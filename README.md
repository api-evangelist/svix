# Svix (svix)

Svix is an enterprise webhooks-as-a-service platform on the sending side of the
webhook market. It provides a single API for delivering reliable, secure, low-latency
webhooks at scale, with hosted UIs (Consumer App Portal), a polyglot SDK pipeline,
an open source server, and adjacent products for streaming (Stream) and webhook
ingestion (Ingest). Hosted offering is multi-region (US, EU, CA, AU, IN) with
SOC 2 Type II, HIPAA, PCI-DSS attestations.

**APIs.json:** [https://github.com/api-evangelist/svix](https://github.com/api-evangelist/svix)

## Scope

- **Type:** Index

## Tags

- Webhooks
- Webhooks As A Service
- Webhook Delivery
- Webhook Sending
- Event Driven
- Eventing
- Messaging
- Pub Sub
- Streaming
- Ingest
- Integration
- Reliability
- Retries
- Deliverability
- Signing
- Verification
- HMAC
- Standard Webhooks
- Multi Tenant
- Multi Region
- Enterprise
- SaaS
- Developer Platform
- API
- REST
- SOC 2
- HIPAA
- PCI DSS
- GDPR
- Open Source
- Rust
- Polyglot SDK
- Terraform
- CLI

## Timestamps

- **Created:** 2026-05-22
- **Modified:** 2026-05-22

## APIs

### Svix Webhooks API

The hosted Svix API for sending webhooks to your customers' endpoints. Covers
applications (tenants), endpoints (subscriber URLs), event types, messages
(webhook payloads), message attempts (delivery history), integrations
(per-application API keys), and the authentication endpoints used to mint
Consumer App Portal access tokens. Also includes operational webhooks (Svix
telling you about your own Svix account), statistics, environment
import/export, background tasks, and connectors.

- **Human URL:** [https://api.svix.com/docs](https://api.svix.com/docs)
- **Base URL:** `https://api.svix.com`

#### Tags

- Webhooks
- Webhook Sending
- Applications
- Endpoints
- Messages
- Message Attempts
- Event Types
- Integrations
- Operational Webhooks
- Background Tasks
- Statistics
- Connectors
- Environments

#### Properties

- [OpenAPI](openapi/svix-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/svix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/svix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.svix.com)
- [API Reference](https://api.svix.com/docs)
- [Authentication](https://docs.svix.com/api-keys)
- [Errors](https://docs.svix.com/retries)
- [Rate Limits](rate-limits/svix-rate-limits.yml)

### Svix Ingest API

The receiving-side surface of Svix. Ingest sources are URLs that accept
incoming webhooks from third parties (Stripe, GitHub, Shopify, etc.), apply
verification, transformations, and forward them to your endpoints. Same
Bearer token, same multi-region hosts, exposed under the /ingest/api/v1/
prefix of the same hosted OpenAPI.

- **Human URL:** [https://api.svix.com/docs](https://api.svix.com/docs)
- **Base URL:** `https://api.svix.com`

#### Tags

- Ingest
- Webhook Receiving
- Sources
- Verification
- Transformation
- Inbound Webhooks

#### Properties

- [OpenAPI](openapi/svix-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/svix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/svix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://www.svix.com/ingest/)
- [API Reference](https://api.svix.com/docs)

### Svix Stream API

Svix Stream is event streaming for product telemetry — sinks, events, and
pollers exposed under /api/v1/stream/. Provides the same delivery-reliability
semantics as webhooks but designed for high-volume event fan-out and pull-based
consumption.

- **Human URL:** [https://www.svix.com/stream/](https://www.svix.com/stream/)
- **Base URL:** `https://api.svix.com`

#### Tags

- Streaming
- Event Stream
- Sinks
- Pollers
- Telemetry

#### Properties

- [OpenAPI](openapi/svix-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/svix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/svix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://www.svix.com/stream/)

### Svix Open Source Server API

The self-hostable open source Svix server (svix-webhooks repo). Smaller surface
area than the hosted product (no Stream, no Ingest, no Connectors, no
Background Tasks, no multi-region) — 29 paths, 46 operations in v1.1.1 — but
API-compatible with the hosted product for the core webhook-sending workflow.

- **Human URL:** [https://github.com/svix/svix-webhooks](https://github.com/svix/svix-webhooks)
- **Base URL:** `http://localhost:8071`

#### Tags

- Open Source
- Self Hosted
- Webhook Sending
- Rust
- MIT License

#### Properties

- [GitHub Repository](https://github.com/svix/svix-webhooks)
- [Documentation](https://docs.svix.com/)
- [Postman Collection](collections/svix.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/svix.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Portal](https://www.svix.com)
- [Developer Portal](https://dashboard.svix.com)
- [Documentation](https://docs.svix.com)
- [API Reference](https://api.svix.com/docs)
- [Getting Started](https://docs.svix.com/quickstart)
- [Quickstart](https://docs.svix.com/quickstart)
- [Tutorials](https://docs.svix.com/tutorials)
- [Sign Up](https://dashboard.svix.com)
- [Login](https://dashboard.svix.com)
- [Pricing](https://www.svix.com/pricing/)
- [Plans](plans/svix-plans-pricing.yml)
- [Rate Limits](rate-limits/svix-rate-limits.yml)
- [Fin Ops](finops/svix-finops.yml)
- [Regions](https://docs.svix.com/multi-region)
- [Authentication](https://docs.svix.com/api-keys)
- [Security](https://www.svix.com/security/)
- [Compliance](https://www.svix.com/security/)
- [Trust Center](https://www.svix.com/security/)
- [Terms of Service](https://www.svix.com/terms/)
- [Privacy Policy](https://www.svix.com/privacy/)
- [Status Page](https://status.svix.com)
- [Blog](https://www.svix.com/blog/)
- [Changelog](https://github.com/svix/svix-webhooks/blob/main/ChangeLog.md)
- [Release Notes](https://github.com/svix/svix-webhooks/releases)
- [Support](mailto:support@svix.com)
- [Contact](https://www.svix.com/contact/)
- [GitHub Organization](https://github.com/svix)
- [GitHub Repository](https://github.com/svix/svix-webhooks)
- [Console](https://dashboard.svix.com)
- [Sandbox](https://play.svix.com)
- [C L I](https://github.com/svix/svix-webhooks/tree/main/svix-cli)
- [SDK](https://pypi.org/project/svix/)
- [SDK](https://www.npmjs.com/package/svix)
- [SDK](https://github.com/svix/svix-webhooks/tree/main/go)
- [SDK](https://central.sonatype.com/artifact/com.svix/svix)
- [SDK](https://github.com/svix/svix-webhooks/tree/main/kotlin)
- [SDK](https://rubygems.org/gems/svix)
- [SDK](https://www.nuget.org/packages/Svix)
- [SDK](https://packagist.org/packages/svix/svix)
- [SDK](https://crates.io/crates/svix)
- [Integrations](https://github.com/svix/terraform-provider-svix)
- [Integrations](https://docs.svix.com/integrations/zapier)
- [Integrations](https://docs.svix.com/integrations/ngrok)
- [X (Twitter)](https://twitter.com/SvixHQ)
- [LinkedIn](https://www.linkedin.com/company/svix)
- [Capabilities](capabilities/)
- [Rules](rules/svix-rules.yml)
- [JSON Schema](json-schema/) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/svix-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](vocabulary/svix-vocabulary.yml)
- [L L Ms Txt](https://docs.svix.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
