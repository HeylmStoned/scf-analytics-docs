# Web and API Analytics for Stellar Ecosystem Projects

Technical design for the SCF #46 RFP. Shared, free, privacy-first analytics for Stellar projects. SCF operators get one comparable view of real usage.

Base product: **Umami** (MIT, TypeScript, Node.js, PostgreSQL). We fork it and add Stellar tenancy, an SCF operator view, and an OpenTelemetry metrics collector. GoatCounter is written in Go. It already records pageviews, referrers, browser, operating system, screen size, and country. It does not compute bounce rate or visit duration. Those two are required, and Umami already computes both.

## In this book

* [System architecture](architecture.md) — one pinned script for the site, one second OpenTelemetry export for the API.
* [Infrastructure](infrastructure.md) — Cloudflare for the tracker, two app replicas, Supabase Postgres in the region the project chooses.
* [Web analytics](web-analytics.md) — the browser script, the required metrics, bots, and the supply chain.
* [API analytics](api-analytics.md) — what the collector keeps, and what it drops.
* [Tenants, isolation, and keys](tenants.md) — enrollment, removal, row-level security, and operator keys.
* [Privacy and compliance](privacy.md) — region chosen by the project, no cookies, country only.
* [Operations and handover](operations.md) — 99.9%, support, and the month 6–12 handover.
* [Plain-English stack](stack.md) — the same design in one paragraph.
