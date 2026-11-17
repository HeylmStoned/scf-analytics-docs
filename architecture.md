# System architecture

```mermaid
flowchart TB
  subgraph Tenants["Stellar projects"]
    Site["Website<br/>static, SPA, or SSR"]
    Api["API service<br/>dual-export OTel"]
  end

  subgraph Edge["Cloudflare"]
    Script["Pinned tracker<br/>/s/vX.Y.Z/s.js + SRI"]
    Waf["DNS, TLS, WAF"]
  end

  subgraph Service["SCF analytics service"]
    WebIn["Web collect<br/>POST /s/e"]
    OtelIn["OTLP collector<br/>traces, metrics, logs in"]
    Drop["Drop spans, traces, logs<br/>keep route, status, latency"]
    Norm["Hard-coded path normalizer<br/>ids, UUIDs, G/C/M, hashes"]
    Dash["Dashboards"]
    TenantView["Tenant view<br/>own web + API only"]
    ScfView["SCF operator view<br/>compare all projects"]
    Keys["Operator API keys<br/>create and revoke"]
  end

  subgraph Data["Supabase Postgres<br/>region chosen by the project"]
    WebDb[("Web aggregates")]
    ApiDb[("API aggregates<br/>24 months")]
    Rls["Row-level security<br/>tenant_id"]
  end

  Site --> Script
  Script --> WebIn
  Api --> OtelIn
  OtelIn --> Drop --> Norm --> ApiDb
  WebIn --> WebDb
  WebDb --> Rls
  ApiDb --> Rls
  Rls --> TenantView
  Rls --> ScfView
  Dash --> TenantView
  Dash --> ScfView
  Keys --> ScfView
  Waf --> WebIn
  Waf --> OtelIn
```

A project adds one pinned script tag for the website, and points its existing OpenTelemetry exporter at our collector as a second destination. Nothing else changes in the app. We never store their traces.
