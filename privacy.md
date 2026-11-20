# Privacy and compliance

Each enrolled project chooses a Supabase residency region at enroll. Its analytics live only in that regional Supabase project. We do not cross-replicate tenant rows between regions. Platform account, billing, and some ops telemetry may still be processed outside that region by Supabase; the Postgres analytics for the tenant stay in the chosen region. The goal is GDPR and UK PECR compliance **without** a cookie banner.

* No cookies, no `localStorage`, no `sessionStorage`.
* Stock Umami can store city, region, and ad click ids such as `gclid`. The fork keeps country and does not store city, region, or those click ids.
* The IP is cut down before it is used (IPv4 last octet dropped, IPv6 kept to /48). The full address is not written to Postgres. Edge logs are not copied into the analytics database.
* The daily visitor hash cannot be recomputed once that day’s random salt is deleted.
* We do not store a name, email, wallet address, or account id. `umami.identify()` is disabled, so a project cannot attach one.
* A tenant can delete its property and the rows that belong to it. That is the erasure path if a row is later treated as personal data.
* We will publish this as the privacy note in the repo. If a regulator treats a third-party script itself as requiring opt-in even with no terminal storage, we will say so and name that jurisdiction before launch rather than ship a banner-based workaround. Germany is the one we will check explicitly. We will not claim a country we have not checked.
