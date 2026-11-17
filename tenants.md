# Tenants, isolation, and keys

* A Stellar project enrolls itself: name, site origin, and one proof that it is on Stellar (a `stellar.toml` on that domain, a Soroban contract id, or an SCF project link).
* SCF operators can remove a project that is not part of the ecosystem.
* Enrollment starts open. A single setting switches it to approval-required later. No schema change.
* A tenant login can read only that tenant’s rows. Postgres row-level security enforces this even if an application query forgets the filter.
* SCF operators are a separate role with the global view. They are not a member of every tenant.
* Operators create and revoke API keys for downstream tools. Keys are stored hashed, and each key is either global or bound to one tenant.
* The service charges nothing.
