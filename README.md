# Web and API Analytics for Stellar Ecosystem Projects

Shared, free, privacy-first analytics for Stellar projects. SCF operators get one comparable view of real usage.

Base product: **Umami** (MIT, TypeScript, Node.js, PostgreSQL). We fork it and add Stellar tenancy, an SCF operator view, and an OpenTelemetry metrics collector. GoatCounter is written in Go. It already records pageviews, referrers, browser, operating system, screen size, and country. It does not compute bounce rate or visit duration. Those two are required, and Umami already computes both.

## Availability commitments

Published here and in the console repository README:

| Target | RFP | Our commitment |
| --- | --- | --- |
| Data collection (ingest) availability | 99.99% | **99.9%** — we will not commit above Supabase’s published platform uptime and a two-replica app tier without uncosted active-active failover |
| Dashboard availability | 99.90% | **99.9%** |
| Critical / high vulnerability remediation | 24 hours | **24 hours** |
| Support: initial response, then resolution | 5 then 10 business days | **5 then 10 business days** |

## In this book

* [System architecture](architecture.md) — full design: flows, components, sizing, and stack summary.
* [Infrastructure](infrastructure.md) — Cloudflare tracker, Redis buffer, Frankfurt Supabase, Compose handover.
* [Web analytics](web-analytics.md) — browser script, required metrics, bots, supply chain.
* [API analytics](api-analytics.md) — collector keep/drop rules and normalization.
* [Tenants, isolation, and keys](tenants.md) — enrollment, RLS, operator keys.
* [Privacy and compliance](privacy.md) — Frankfurt residency, minimisation, erasure.
* [Privacy notice](privacy-notice.md) — short tenant-facing notice.
* [Operations and handover](operations.md) — availability table, support, handover.
* [What works today / what’s next](status.md) — POC vs the nine delivery items.
* [Contributors agreement](contributors-agreement.md) — how contributions are accepted.
* [Release history](release-history.md) — public design and POC releases.
* [Plain-English stack](stack.md) — one-paragraph summary.
