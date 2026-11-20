# Tenants, isolation, and keys

* A Stellar project enrolls itself: name, site origin, chosen EU residency region (Frankfurt or London at launch), and one proof that it is on Stellar (a `stellar.toml` on that domain, a Soroban contract id, or an SCF project link).
* The residency region maps to one Supabase project. That tenant’s data is written and read only there.
* Enrollment does not list a project on the dashboard. Listing is separate, and SCF decides what is shown.
* SCF operators can remove a project that is not part of the ecosystem.
* Enrollment starts open. A single setting switches it to approval-required later. No schema change.
* A tenant login can read only that tenant’s rows. Postgres row-level security enforces this even if an application query forgets the filter.
* SCF operators are a separate role with the global view. They are not a member of every tenant.
* Operators create and revoke API keys for downstream tools. Keys are stored hashed, and each key is either global or bound to one tenant.
* The service charges nothing.
