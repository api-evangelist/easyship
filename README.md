# Easyship (easyship)

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

Easyship is a comprehensive all-in-one shipping platform headquartered in Hong Kong that provides e-commerce businesses with a one-stop solution for their shipping needs. From comparing rates and services across 250+ couriers to managing orders, generating labels, scheduling pickups, calculating duties and taxes, and tracking shipments, Easyship streamlines cross-border and domestic logistics for businesses of all sizes. The Easyship REST API exposes the same shipping engine that powers the Easyship dashboard and platform integrations to developers building custom commerce, fulfillment, and logistics workflows.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Shipping
- Logistics
- Ecommerce
- Fulfillment
- CrossBorder

## Timestamps

- **Created:** 2025-03-01
- **Modified:** 2026-05-25

## APIs

### Easyship API

The Easyship API allows e-commerce platforms and merchants to programmatically compare carrier rates across 250+ integrated couriers, generate shipping labels, manage shipments and tracking, schedule courier pickups, handle returns, and calculate duties and taxes for international parcels. Authentication uses OAuth 2.0 bearer tokens and the surface includes shipments, rates, labels, addresses, pickups, trackings, manifests, webhooks, products, boxes, and insurance.

- **Human URL:** [https://developers.easyship.com/](https://developers.easyship.com/)
- **Base URL:** `https://api.easyship.com`

#### Tags

- Shipping
- Logistics
- Ecommerce
- CrossBorder

#### Properties

- [Documentation](https://developers.easyship.com/docs)
- [Reference](https://developers.easyship.com/reference)
- [Getting Started](https://developers.easyship.com/reference/getting-started)
- [Authentication](https://developers.easyship.com/reference/authentication)
- [Recipes](https://developers.easyship.com/recipes)
- [Changelog](https://developers.easyship.com/changelog)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/openapi/easyship-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/json-schema/easyship-shipment-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/json-schema/easyship-rate-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/json-schema/easyship-label-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/json-schema/easyship-tracking-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/json-schema/easyship-webhook-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/json-structure/easyship-structure.json)
- [JSON-LD](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/json-ld/easyship-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Spectral Rules](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/rules/easyship-rules.yml)
- [Vocabulary](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/vocabulary/easyship-vocabulary.yml)
- [Example](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/examples/easyship-get-rates-example.json)
- [Example](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/examples/easyship-create-label-example.json)
- [Plans](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/plans/easyship-plans-pricing.yml)
- [Rate Limits](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/rate-limits/easyship-rate-limits.yml)
- [Fin Ops](https://raw.githubusercontent.com/api-evangelist/easyship/refs/heads/main/finops/easyship-finops.yml)
- [Postman Collection](collections/easyship.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/easyship.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/easyship)
- [LinkedIn](https://www.linkedin.com/company/easyship)
- [Website](https://www.easyship.com/)
- [Developer  Portal](https://developers.easyship.com/)
- [Pricing](https://www.easyship.com/pricing)
- [Sign Up](https://app.easyship.com/login)
- [Support](https://support.easyship.com/)
- [Blog](https://www.easyship.com/blog)
- [Status Page](https://status.easyship.com/)
- [Integrations](https://www.easyship.com/integrations)
- [L L Ms Txt](https://developers.easyship.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
