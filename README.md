# Svix

[Svix](https://www.svix.com) is an enterprise webhooks-as-a-service platform that sits on the **sending side** of the webhook market. Where receiving-side providers like Hookdeck specialize in consuming inbound webhooks, Svix specializes in helping platforms ship reliable, low-latency, signed webhooks to their own customers' subscriber URLs at scale — with hosted UIs, a polyglot SDK pipeline, an open source self-hostable server, and adjacent products for event streaming (Stream) and inbound ingestion (Ingest).

> "Svix makes sending webhooks easy and reliable by offering webhook sending as a service." — [docs.svix.com](https://docs.svix.com)

This repository is the API Evangelist profile of Svix: the inventory of every API surface they expose, the OpenAPI of the hosted product, plus generated capabilities, JSON Schemas, vocabulary, plans, rate limits, and FinOps artifacts.

## APIs Documented

| API | Description | Spec |
|---|---|---|
| **Svix Webhooks API** | The core hosted sending surface — apps, endpoints, event types, messages, attempts, integrations, operational webhooks, background tasks, statistics, environments, connectors. | [`openapi/svix-openapi.json`](openapi/svix-openapi.json) |
| **Svix Ingest API** | Receiving-side surface (`/ingest/api/v1/`) — sources, ingest endpoints, transformations. Same OpenAPI document. | [`openapi/svix-openapi.json`](openapi/svix-openapi.json) |
| **Svix Stream API** | Event streaming (`/api/v1/stream/`) — streams, stream event types, sinks, pollers. Same OpenAPI document. | [`openapi/svix-openapi.json`](openapi/svix-openapi.json) |
| **Svix Open Source Server** | Self-hostable subset of the hosted product (`server/openapi.json` in `svix/svix-webhooks`, MIT licensed, Rust). | upstream: [svix/svix-webhooks](https://github.com/svix/svix-webhooks/blob/main/server/openapi.json) |

### Scale of the hosted OpenAPI

- **OpenAPI version**: 3.x
- **Info version**: `1.84.0`
- **Paths**: 79
- **Operations**: 128
- **Tag groups**: 15 (Application, Message, Message Attempt, Endpoint, Integration, Event Type, Authentication, Health, Webhook, Background Task, Statistics, Webhook Endpoint, Environment, Ingest Endpoint, Connector)
- **Components.schemas**: 461
- **Regions**: 5 — `api.us.svix.com`, `api.eu.svix.com`, `api.ca.svix.com`, `api.au.svix.com`, `api.in.svix.com`
- **Authentication**: HTTP Bearer (token from [dashboard.svix.com](https://dashboard.svix.com))

The open source server's spec is a smaller, focused subset: 29 paths, 46 operations, 64 schemas at `info.version` `1.1.1`.

## Repository Layout

```
svix/
├── apis.yml                # Master index for this provider
├── README.md
├── openapi/                # Hosted-product OpenAPI spec
│   └── svix-openapi.json
├── examples/               # Request / response examples for key operations
├── rules/                  # Spectral ruleset capturing Svix conventions
│   └── svix-rules.yml
├── capabilities/           # Naftiko capabilities
│   ├── shared/             #   Shared per-API capabilities
│   │   ├── svix-webhooks.yaml
│   │   ├── svix-ingest.yaml
│   │   └── svix-stream.yaml
│   ├── customer-webhook-onboarding.yaml
│   ├── failed-delivery-recovery.yaml
│   └── third-party-webhook-fan-in.yaml
├── json-schema/            # JSON Schema for Application, Endpoint, Message, MessageAttempt, EventType
├── json-structure/         # JSON Structure (field/relation metadata) for the same entities
├── json-ld/                # JSON-LD context aligned with schema.org + standardwebhooks.com
│   └── svix-context.jsonld
├── vocabulary/             # Operational + capability vocabulary
│   └── svix-vocabulary.yml
├── plans/                  # API Commons Plans 0.1 — Free / Professional / Enterprise
│   └── svix-plans-pricing.yml
├── rate-limits/            # API Commons Rate Limits 0.1
│   └── svix-rate-limits.yml
└── finops/                 # FinOps Framework / FOCUS mapping
    └── svix-finops.yml
```

## Pricing Snapshot

| Plan | Monthly | Included messages | Overage | Max rate | Retention |
|---|---|---|---|---|---|
| Free | $0 | 50,000 / mo | $0.0001 / msg | 200 / s | 30 days |
| Professional | $490 | 50,000 / mo | $0.0001 / msg | 800 / s | 90 days |
| Enterprise | Custom | Custom | Custom | Custom | Custom |

> "Only attempted messages are counted towards usage. Messages filtered by Svix (e.g. when there are no sinks) and retries are both free." — [svix.com/pricing](https://www.svix.com/pricing/)

Enterprise adds OIDC / SAML SSO, on-premises deployment, audit logs, and advanced RBAC.

## Ecosystem

- **SDKs**: Python, JavaScript / TypeScript, Go, Java, Kotlin, Ruby, C# / .NET, PHP, Rust — all generated from the same OpenAPI through a custom Rust-based `openapi-codegen`.
- **CLI**: [svix-cli](https://github.com/svix/svix-webhooks/tree/main/svix-cli) (Go), installable via `brew install svix/svix/svix-cli` or Scoop.
- **Terraform provider**: [`terraform-provider-svix`](https://github.com/svix/terraform-provider-svix).
- **Open source server**: [svix/svix-webhooks](https://github.com/svix/svix-webhooks) — 3.2k+ stars, MIT-licensed, written in Rust on Axum + SeaORM.
- **Standard Webhooks**: Svix is the primary author and maintainer of the [Standard Webhooks](https://www.standardwebhooks.com) specification — the same signing/verification scheme the hosted product implements.
- **Integrations**: Zapier, ngrok, Stripe / GitHub / Shopify / Adyen / Adobe Sign / Airwallex / Checkbook / Azure / S3 (via Ingest connectors).
- **Adjacent products**: Svix Stream (event streaming), Svix Ingest (inbound webhook receiving), Svix Play (test/debug surface at [play.svix.com](https://play.svix.com)), Svix Portal (the consumer-facing UI).

## Compliance & Security

SOC 2 Type II, HIPAA attestation, PCI-DSS attestation, GDPR, CCPA, PIPEDA. Data at rest encrypted with 256-bit AES; HSMs for key storage; TLS 1.2/1.3 in transit. Regional data residency in US, EU, CA, AU, IN.

> "Data persisted by the Svix service is encrypted at rest using 256-bit AES." — [svix.com/security](https://www.svix.com/security/)

## Position In The Market

The webhook market splits into two distinct sides:

- **Sending side** (this provider, Svix): for platforms that *emit* webhooks to their customers. Concerns: fan-out, signing, retries, throttling, customer-facing UIs, schema management, multi-region.
- **Receiving side** (e.g. Hookdeck): for engineering teams that *receive* webhooks from third parties. Concerns: ingestion, verification, transformation, queueing, replay, observability.

Svix has been quietly extending into the receiving side via **Svix Ingest**, but its center of gravity — and the bulk of its OpenAPI surface — is still sending. Its open-sourcing of the server and authorship of the Standard Webhooks spec are how it claims neutrality and category leadership at the same time.

## Links

- Provider site: <https://www.svix.com>
- Docs: <https://docs.svix.com>
- API reference: <https://api.svix.com/docs>
- Dashboard: <https://dashboard.svix.com>
- Status: <https://status.svix.com>
- Blog: <https://www.svix.com/blog/>
- GitHub org: <https://github.com/svix>
- Open source server: <https://github.com/svix/svix-webhooks>
- Standard Webhooks: <https://www.standardwebhooks.com>

---

Maintained as part of the [API Evangelist](https://apievangelist.com) network. See [`apis.yml`](apis.yml) for the structured index used by network-wide tooling.
