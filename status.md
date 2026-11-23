# What works today / what’s next

This page maps the live proof-of-concept and design work to the delivery schedule in the submitted application (**1.1–3.3**).

The console at [scf-console-production.up.railway.app](https://scf-console-production.up.railway.app) is a **UI prototype** for reviewers (Public, SCF, and Tenant modes). It is not the production ingest plane, isolation boundary, or availability target.

### What is real in the POC

- Layouts and flows for ecosystem, operator, and tenant views, plus the delivery roadmap.
- Web aggregates from Umami when demo properties are configured; otherwise documented fixtures.
- API route, status, and latency from the hosted OTLP collector when a tenant dual-exports (Prism is wired). The console labels Live vs Sample from collector coverage.
- Links to this GitBook and the open repositories.

### What is sample in the POC

- API fixtures when the collector has no rows for the selected project, or the collector is unreachable.
- Enrollment, listing, API-key, and erasure actions (session UI only; they reset on reload).
- Production-grade persistence (Redis buffer, Supabase RLS writes) for the collector path — the POC collector is in-memory on Railway until **2.1** hardens that stack.

## Delivery schedule

| No. | Title | Target date | Current state |
| --- | --- | --- | --- |
| **1.1** | Umami Fork and Tenant Isolation | 6 January 2027 | Umami fork public; multi-tenant RLS designed |
| **1.2** | Stellar Enrollment and Verification | 13 January 2027 | Enrollment and verification designed; previewed in the POC |
| **1.3** | Privacy-First Web Tracker | 20 January 2027 | Pinned tracker, SRI, and bot checks specified |
| **2.1** | OpenTelemetry Collector and API Metrics | 10 February 2027 | POC collector live on Railway; Prism dual-export; path normalizer in place; production Redis/Postgres path still ahead |
| **2.2** | Operator Dashboard and API Keys | 24 February 2027 | Operator compare and key flows previewed in the POC |
| **2.3** | Security, Privacy Workflows and Load Testing | 3 March 2027 | Privacy note and threat model published |
| **3.1** | Production Deployment and Monitoring | 17 March 2027 | Availability commitments published; production stack follows this design |
| **3.2** | Pilot Onboarding with SCF-Awarded Projects | 31 March 2027 | Prism and Lend.xyz named; see [Pilots](pilots.md) |
| **3.3** | Handover Kit and Start of 12-Month Operations | 7 April 2027 | Handover plan and Compose-based rebuild path documented |

Source repositories: [scf-analytics-console](https://github.com/HeylmStoned/scf-analytics-console) · [scf-analytics-poc](https://github.com/HeylmStoned/scf-analytics-poc) (OTLP collector) · [scf-analytics-docs](https://github.com/HeylmStoned/scf-analytics-docs) · [scf-umami](https://github.com/HeylmStoned/scf-umami).
