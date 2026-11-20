# What works today / what’s next

Aligned with the nine delivery items below. The interactive console POC is a **UI prototype** (currently hosted on Railway). It is not production ingest, isolation, or availability.

## The nine deliverables

| # | Deliverable | Today | Next |
| --- | --- | --- | --- |
| 1 | Multi-tenant Umami fork + Postgres RLS | Designed; fork repo public; RLS not production-enforced in the POC | Tranche 1 — implement and test isolation on staging |
| 2 | Privacy-first pinned web tracker (`/s/v…/s.js`, SRI, bot checks) | Designed; POC shows integration copy and can read live Umami aggregates when configured | Tranche 1 — ship immutable tracker + collect path |
| 3 | OTLP API collector + hard-coded path normalizer | Designed; POC shows **sample** API metrics and dual-export docs | Tranche 2 — build collector, Redis buffer, hourly aggregates |
| 4 | Tenant dashboards (web + API) | POC tenant mode with demo projects | Tranche 1–2 — wire to real tenant-scoped data |
| 5 | SCF global compare dashboards | POC SCF / Public modes with compare and listing UX | Tranche 2 — production operator controls |
| 6 | Enrollment, listing, keys, erasure | POC session-only demos (reset on reload) | Tranche 2 — durable workflows + hashed keys |
| 7 | MIT monorepo: Compose, Terraform, tests, runbooks | Docs + console + Umami fork public; Compose stub for local rebuild of the POC stack | Through tranche 3 — full production Compose (Umami + collector + Redis + Postgres) |
| 8 | Fresh-environment rebuild + handover video | Not yet — depends on Compose/runbooks | Tranche 3 — record rebuild from repo on a clean host |
| 9 | Live adoption: ≥3 SCF projects (web) + ≥1 (API) | Not yet — consent-based during delivery | Tranche 3 — pilots + operator/tenant screen-capture video |

## What the POC is

* A reviewer console for **Public**, **SCF**, and **Tenant** perspectives.
* **Web** numbers can be **live from Umami** when the demo properties are configured; otherwise fixtures.
* **API** numbers in the POC are **sample / fictional** until the collector ships.
* Enrollment, listing, keys, and erasure in the POC are **UI demos** (session state), not production durability.
* Design source of truth: this GitBook. Console: [scf-analytics-console](https://github.com/HeylmStoned/scf-analytics-console). Live UI: [scf-console-production.up.railway.app](https://scf-console-production.up.railway.app).
