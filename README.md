# Incentivio (incentivio)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Incentivio is a Boston-based digital guest engagement platform for multi-unit restaurant brands, unifying online ordering, loyalty, marketing automation, and guest analytics into a single system. Its Incentivio Connect product is an AI-powered, API-first restaurant data platform that ingests data from POS, loyalty, mobile apps, web, and marketplaces, resolves it into a single persistent Guest ID, and scores guests for lifetime value, churn risk, visit frequency, journey stage, propensity-to-purchase, and offer sensitivity. The platform is BigQuery-native with a Star Schema data model, SOC 2 aligned with encryption at rest and in transit and RBAC, and pairs an API-first surface with reverse ETL to sync unified guest records back to existing CRM and ad platforms. Incentivio is built on modern APIs and offers deep partner integrations with POS, payments, delivery, and marketing systems such as Toast, Oracle Simphony, Square, SpotOn, and PAR Brink. Public, self-service developer API documentation does not appear to be available; integration and API access are handled through partnerships and enterprise onboarding (the Connect Enterprise tier markets dedicated API SLAs).

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/incentivio/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Restaurant, Guest Engagement, Online Ordering, Loyalty, Customer Data Platform, Marketing Automation, Analytics, Reverse ETL

## Timestamps

- **Created:** 2026-06-02
- **Modified:** 2026-06-02

## APIs

### Incentivio Connect Platform API

Incentivio describes an API-first, composable data platform that unifies guest data across POS, loyalty, app, web, and marketplace channels into a single persistent Guest ID, with reverse ETL to sync to existing CRM and ad platforms. Real-time streaming and structured batch ETL process loyalty and digital events alongside structured POS data for guest scoring and segmentation. The platform is BigQuery-native with a Star Schema data model. Public API reference, base URL, and authentication details are not published; access is provided through partner and enterprise integration programs, with API SLAs offered on the Connect Enterprise tier.

**Human URL:** [https://incentivio.com/feature/incentivio-connect/](https://incentivio.com/feature/incentivio-connect/)

#### Tags:

 - Guest Data, Integrations, Reverse ETL

#### Properties

- [Documentation](https://incentivio.com/feature/incentivio-connect/)

## Common Properties

- [Website](https://incentivio.com/)
- [Documentation](https://www.incentivio.com/integrations)
- [Pricing](https://incentivio.com/demo/)
- [Support](https://incentivio.com/contact/)
- [Blog](https://incentivio.com/blog/)
- [SignUp](https://admin.incentivio.com/)
- [LinkedIn](https://www.linkedin.com/company/incentivio)
- [X](https://x.com/incentivio)

## Features

| Name | Description |
|------|-------------|
| Online Ordering | Branded web and native iOS/Android mobile ordering with menu, modifier, upsell recommendations, and gift card support. |
| Loyalty | Configurable points, punch, or tier loyalty programs unified with ordering, marketing, and guest analytics. |
| Marketing Automation | Email and SMS marketing automation driven by unified guest data and AI-derived segments. |
| AI Guest Scoring | Continuous per-guest scoring for lifetime value, churn risk, visit frequency, journey stage, propensity-to-purchase, and offer sensitivity. |
| Unified Guest Identity | One persistent Guest ID resolved across POS, app, web, and loyalty channels for a single guest record. |
| Reverse ETL | Syncs unified guest records and scores back to existing CRM and ad platforms to fit the brand's existing stack. |
| BigQuery-Native Data Warehouse | BigQuery-native platform with a Star Schema data model and direct warehouse access, optimized for enterprise-scale performance. |
| Closed-Loop ROI Measurement | Executive and operator dashboards that tie AI capability to same-store sales growth with closed-loop measurement. |

## Use Cases

| Name | Description |
|------|-------------|
| Multi-Unit Restaurant Brands | Multi-unit and franchise restaurant brands consolidating ordering, loyalty, marketing, and analytics on a single platform. |
| Guest Lifetime Value Growth | Identifying high-LTV and at-risk guests to target retention, frequency, and average-order-value campaigns. |
| POS and Channel Data Unification | Unifying POS, loyalty, app, web, and marketplace data into a single guest record for analytics and personalization. |

## Integrations

| Name | Description |
|------|-------------|
| Toast | POS integration with direct API access auto-syncing menus, modifiers, and rules. |
| Square | POS integration for menu, order, and payment management. |
| Clover | POS integration. |
| Lightspeed | POS integration. |
| Oracle MICROS Simphony | Enterprise POS integration. |
| PAR Brink POS | POS integration. |
| Qu POS | POS integration. |
| Revel | POS integration automating menu imports. |
| Silverware POS | POS integration. |
| SpotOn | POS and engagement platform integration with automatic menu syncing. |
| NCC | POS integration. |
| Stripe | Payment processing integration. |
| Braintree | Payment processing integration. |
| Authorize.net | Payment processing integration. |
| Heartland Payment Systems | Payment processing integration. |
| Moneris | Payment processing integration. |
| Spreedly | Payments orchestration integration. |
| WorldPay | Payment processing integration. |
| DoorDash Drive | Delivery dispatch integration. |
| Uber | Delivery integration. |
| dlivrd | Delivery dispatch integration. |
| Shipday | Delivery dispatch integration. |
| Otter | Delivery/marketplace aggregator integration. |
| EatOkra | Discovery/marketplace aggregator integration. |
| Ovation | Guest feedback integration. |
| Tattle | Guest feedback and experience improvement integration. |

## Solutions

| Name | Description |
|------|-------------|
| Connect Core | Unified data warehouse with executive dashboards and direct warehouse access. |
| Connect Intelligence | Adds the full AI scoring suite (LTV, churn, propensity, offer sensitivity) and closed-loop measurement on top of Core. |
| Connect Enterprise | Dedicated instance with custom data models, API SLAs, and white-glove implementation. |

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
