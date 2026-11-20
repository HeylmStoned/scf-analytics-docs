# Operations and handover

Commitments for the 12 months after the final development tranche is approved. The same numbers are published here and in the repository README.

| Target | RFP | Our commitment |
| --- | --- | --- |
| Data collection (ingest) availability | 99.99% | **99.9%** |
| Dashboard availability | 99.90% | **99.9%** |
| Critical and high vulnerability remediation | 24 hours | **24 hours** |
| Support: initial response, then resolution | 5 then 10 business days | **5 then 10 business days** |

**Ingest 99.9% (below the RFP’s 99.99%):** we will not commit above Supabase’s published platform uptime and a two-replica app tier without inventing multi-region active-active failover we have not costed. Dashboard 99.9% meets or exceeds the RFP’s 99.90% dashboard figure.

Support is via public GitHub issues. No mandatory on-call rotation and no private support desk. Incident severity is triage priority on that tracker; response clocks follow the 5 / 10 business-day commitment above.

## Monitoring

Uptime, Redis buffer depth, ingest latency, and database health are monitored, with alerts to the designated operator contact during business hours. Ops dashboards ship in the handover pack.

## Handover

Any time from month 6 to month 12, at SCF’s discretion:

* Repository ownership moves to the operator SCF names.
* Full Postgres dump and restore.
* Domain transfer, or a permanent redirect from the old domain.
* The new operator brings the system up from Docker Compose / Terraform in the monorepo. They do not need our Cloudflare or Supabase accounts.

The monorepo is MIT-licensed and contains the Umami fork, the collector, the tracker, Compose (app + collector + Redis + Postgres), Terraform, tests, the tenant guide, the operator runbook, and the privacy note.

Daily database snapshots, 30-day retention, restore test each quarter.
