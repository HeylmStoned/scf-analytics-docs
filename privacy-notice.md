# Privacy notice (tenant template)

**Service:** Pulse — shared web and API analytics for Stellar projects  
**Operator (during the hosting window):** the proposing team, then the community operator named by SCF at handover  
**Data location:** Frankfurt, Germany (`eu-central-1`)

## What we collect

**Web (browser script only):** page path, referrer, country (from a truncated IP that is then discarded), device and browser class, bounce and session aggregates. No cookies. No `localStorage` / `sessionStorage`. No names, emails, wallet addresses, or account IDs.

**API (OpenTelemetry dual-export):** normalized route, HTTP method, status code, latency histograms, tenant and service identifiers you configure. Traces, spans, and deep logs are dropped and not stored.

## Legal basis and minimisation

The service is designed for GDPR / UK PECR compliance without a cookie banner, by minimising data. Visitor identifiers use a truncated IP, user agent, and a salt that is deleted daily so visitors are not linkable across days.

## Retention

* Raw debug events: up to 14 days  
* Aggregates: 24 months  
* After you delete a property: tenant rows removed within 30 days  

## Your controls

* Export aggregates (CSV) from your tenant dashboard  
* Delete your property (erasure workflow)  
* Rotate ingest keys  

## Contact

Use the public GitHub issue tracker for the operator named in the live deployment. Response within 5 business days; resolution within 10 business days for support tickets.
