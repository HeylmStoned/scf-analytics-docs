# Operations and handover

Commitments for the 12 months after the final development tranche is approved:

| Target | Commitment |
| --- | --- |
| Ingest availability | 99.9% |
| Dashboard availability | 99.9% |
| Critical and high vulnerabilities | Patched within 24 hours |
| Support | GitHub issues. Reply in 5 business days, closed in 10. |

Supabase's published uptime commitment is 99.9%, and only on Enterprise. Pro and Team have no uptime SLA. We commit to 99.9% for ingest and for the dashboard because that is the database contract. The RFP names 99.99% ingest as the figure to compete on. We will not sign a higher number than the database supports.

No on-call rotation and no private support desk.

## Handover

Any time from month 6 to month 12:

* Repository ownership moves to the operator SCF names.
* Full Postgres dump and restore.
* Domain transfer, or a permanent redirect from the old domain.
* The new operator brings the system up from the monorepo. They do not need our Cloudflare or Supabase accounts.

The monorepo is MIT-licensed and contains the Umami fork, the collector, the tracker, Compose, Terraform, tests, the tenant guide, the operator runbook, and this privacy note.

This is a shared service on purpose, so every project is measured the same way. The software is open and rebuildable so that operation can move. The data is not a token and not a chain.
