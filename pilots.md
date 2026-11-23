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

Lend.xyz is named in the application as an early pilot alongside Prism. The public agreement record (scope — web and/or API — date, and link or message with consent) will be published on this page when it is available.

## Further pilots

The RFP asks for at least three SCF-awarded projects on web analytics and one project on API traffic. Each new agreement is added here with project name, connection type, date, and a public proof link.
