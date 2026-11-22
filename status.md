# What works today / what’s next

Aligned with the **submitted form deliverables (1.1–3.3)**. The interactive console POC is a **UI prototype** (hosted on Railway). It is not production ingest, isolation, or availability.

## Deliverables (form numbering)

| No. | Title | Date | Today | Next |
| --- | --- | --- | --- | --- |
| **1.1** | Umami Fork and Tenant Isolation | January 6, 2027 | Fork public (`scf-umami`); tenancy/RLS designed; not production-enforced in the POC | Implement and test RLS + tenant core on staging |
| **1.2** | Stellar Enrollment and Verification | January 13, 2027 | Enrollment UX previewed in POC (session-only) | Durable enrollment + `stellar.toml` / contract / SCF-link checks |
| **1.3** | Privacy-First Web Tracker | January 20, 2027 | Designed; POC shows integration copy; can read live Umami aggregates when configured | Ship pinned `/s/v…/s.js` + SRI + bot/Origin checks |
| **2.1** | OpenTelemetry Collector and API Metrics | February 10, 2027 | Designed; POC shows **sample** API metrics + dual-export docs | Build collector, Redis buffer, hourly aggregates |
| **2.2** | Operator Dashboard and API Keys | February 24, 2027 | POC SCF / Public modes with compare, listing, and key UI demos | Production operator controls + hashed, revocable keys |
| **2.3** | Security, Privacy Workflows and Load Testing | March 3, 2027 | Privacy note + threat model documented; erase UI is session-only | Durable erasure, pen-test prep, ~1M req/day load validation |
| **3.1** | Production Deployment and Monitoring | March 17, 2027 | POC on Railway (UI only); ops commitments published | Production stack + monitoring dashboards |
| **3.2** | Pilot Onboarding with SCF-Awarded Projects | March 31, 2027 | Prism + Lend.xyz named; Prism web instrumentation started — see [Pilots](pilots.md) | Finish proofs; third web pilot; name API pilot; onboard |
| **3.3** | Handover Kit and Start of 12-Month Operations | April 7, 2027 | Docs + Compose stub for POC; handover plan written | Full Compose/Terraform, rebuild video, 12-month window starts |

## What the POC is

* A reviewer console for **Public**, **SCF**, and **Tenant** perspectives.
* **Web** numbers can be **live from Umami** when demo properties are configured; otherwise fixtures.
* **API** numbers in the POC are **sample / fictional** until deliverable 2.1 ships.
* Enrollment, listing, keys, and erasure in the POC are **UI demos** (session state), not production durability.
* Design source of truth: this GitBook. Console: [scf-analytics-console](https://github.com/HeylmStoned/scf-analytics-console). Live UI: [scf-console-production.up.railway.app](https://scf-console-production.up.railway.app).
