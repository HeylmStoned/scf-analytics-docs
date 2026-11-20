# Infrastructure

```mermaid
flowchart TB
  subgraph CF["Cloudflare"]
    DNS["DNS, TLS, WAF"]
    Assets["Immutable tracker files<br/>one URL per version"]
    Q["Cloudflare Queues<br/>durable admission"]
  end

  subgraph App["Two app replicas"]
    Umami["Umami fork<br/>collect + dashboards"]
    Collector["OTLP collector"]
  end

  subgraph Store["Supabase"]
    PG[("One Postgres project<br/>per EU residency region")]
  end

  subgraph Handback["Handover"]
    Compose["Docker Compose<br/>app + collector + Postgres"]
  end

  DNS --> Umami
  DNS --> Collector
  Assets --> Umami
  Umami --> Q --> PG
  Collector --> Q
  Compose --> PG
```

* **Tracker files** are static and versioned on Cloudflare. A release never changes a URL that tenants already embedded.
* **Umami and the collector** run as two stateless replicas. Umami is a Node server. The collector has to parse full OpenTelemetry payloads. The tracker file is the piece that stays on Cloudflare.
* **Durable admission** uses Cloudflare Queues. Validated web events and normalised API metric batches are written to the queue before Postgres. If the writer is down, already-admitted traffic is not lost. Redis is not the ingest buffer.
* **Postgres** is Supabase. A Supabase project is bound to one region. At launch we offer **EU regions only** (Frankfurt and London). At enrollment the tenant chooses a region; every later read and write for that tenant goes only to that project. We do **not** replicate tenant analytics across regions. Edge routing (tenant → region → connection) is how the edge and the app pick the right database. More tenants do not mean more regions; regions stay fixed, and each regional database scales inside its region.
* Umami does not ship row-level security. We add it, and every analytics read and write is bound to `tenant_id` inside that regional project.
* **Docker Compose** in the same monorepo is how the next operator rebuilds the system. Terraform is included for the hosted setup. The compose file is the handover contract.
* Design load is about **1,000,000 API requests per day** (about 12 requests/second average, sized for 100/second peaks). Web traffic is smaller than that.
* The public console POC may run on Railway as a **UI prototype**. That is not production hosting; production follows this stack.
