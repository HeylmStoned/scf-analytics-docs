# Pilots

Pulse ships with named early adopters so SCF can see real instrumentation, not only fixtures. The application names **Prism** and **Lend.xyz** as the first pilots. Additional SCF-awarded projects join this page when each agreement is public.

## Prism

Prism is the team’s production DEX frontend. It is the first web pilot, and it also dual-exports API telemetry to the POC OTLP collector.

| | |
| --- | --- |
| **Connection** | Web analytics (browser tracker) and API (OTLP dual-export) |
| **Instrumentation** | Umami Cloud script on the production app; OTLP/HTTP spans to the hosted collector |
| **Public proof** | Live web and API rows in the [reviewer console](https://scf-console-production.up.railway.app) (Tenant → Prism / `beta`) · collector [scf-analytics-poc](https://github.com/HeylmStoned/scf-analytics-poc) · integration notes in [API analytics](api-analytics.md) |

The production Prism application repository stays private. Reviewers verify instrumentation through the public POC console and collector, not through the private app repo.

## Lend.xyz

Lend.xyz is named in the SCF application as an early web pilot alongside Prism. The Umami property for `app.lend.xyz` is registered in the operator workspace, but the production site has **not** shipped the Umami script yet — so there are still no recorded pageviews.

| | |
| --- | --- |
| **Connection** | Web analytics (browser tracker) — agreed scope for the pilot |
| **Instrumentation** | Not live on [app.lend.xyz](https://app.lend.xyz) yet. A Umami website for `app.lend.xyz` is already enrolled so traffic can appear as soon as the script is pinned. |
| **Public proof** | Named pilot in the application · Umami property visible under **SCF → SCF managing** in the [reviewer console](https://scf-console-production.up.railway.app) (status: no pageviews until the script is installed) · site: [lend.xyz](https://lend.xyz) |

When Lend.xyz installs the tracker, the same managing row should move from “no pageviews” to live web metrics without a new enrollment. A dated consent message or agreement link can be added here when the team publishes one; this page does not invent that record.

## Further pilots

The RFP asks for at least three SCF-awarded projects on web analytics and one project on API traffic. Each new agreement is added here with project name, connection type, date, and a public proof link.
