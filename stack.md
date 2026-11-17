# Plain-English stack

Umami, forked, serves the script, the web dashboard, and the per-project login. A small OpenTelemetry collector next to it turns API telemetry into hourly counts and latency histograms, and deletes the traces. Both write to Postgres in Frankfurt, with row-level security per project. Cloudflare serves the version-pinned script and terminates TLS. Docker Compose is how someone else runs it after handover. Stellar shows up in enrollment (`stellar.toml` or a contract id) and in the path normalizer (`G…`, `C…`, and `M…` addresses), not as a place we write analytics to.
