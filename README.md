# Svix (svix)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
