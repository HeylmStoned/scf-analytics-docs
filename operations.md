# Operations and handover

Commitments for the 12 months after the final development tranche is approved:

| Target | Commitment |
| --- | --- |
| Ingest availability | 99.9% (explicit deviation from RFP 99.99% ingest — see below) |
| Dashboard availability | 99.9% (matches RFP 99.90%) |
| Critical and high vulnerabilities | Patched within 24 hours |
| Support | GitHub issues. Reply in 5 business days, closed in 10. |

**Deviation from the RFP:** the RFP lists 99.99% ingest as a figure proposers compete on. We commit to 99.9% for ingest and for the dashboard because that is the uptime we can operate credibly against Supabase’s published platform commitment and a two-replica app tier, without inventing multi-region active-active failover we have not costed. We will not sign a higher number than we can support.

No on-call rotation and no private support desk. Incident severity is used for triage priority on the public tracker; response clocks follow the GitHub support commitment above, not a 24/7 pager.

## Handover

Any time from month 6 to month 12:

* Repository ownership moves to the operator SCF names.
* Full Postgres dump and restore.
* Domain transfer, or a permanent redirect from the old domain.
* The new operator brings the system up from the monorepo. They do not need our Cloudflare or Supabase accounts.

The monorepo is MIT-licensed and contains the Umami fork, the collector, the tracker, Compose, Terraform, tests, the tenant guide, the operator runbook, and this privacy note.

This is a shared service on purpose, so every project is measured the same way. The software is open and rebuildable so that operation can move. The data is not a token and not a chain.
