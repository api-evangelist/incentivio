# Incentivio

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

Incentivio is a Boston-based digital guest engagement platform for multi-unit restaurant brands, unifying online ordering, loyalty, marketing automation, and guest analytics into a single system. Its Incentivio Connect product is an AI-powered, API-first restaurant data platform that ingests data from POS, loyalty, mobile apps, web, and marketplaces, resolves it into a single persistent Guest ID, and scores guests for lifetime value, churn risk, visit frequency, journey stage, propensity-to-purchase, and offer sensitivity. The platform is BigQuery-native with a Star Schema data model, SOC 2 aligned with encryption at rest and in transit and RBAC, and pairs an API-first surface with reverse ETL to sync unified guest records back to existing CRM and ad platforms. Incentivio is built on modern APIs and offers deep partner integrations with POS, payments, delivery, and marketing systems such as Toast, Oracle Simphony, Square, SpotOn, and PAR Brink. Incentivio runs a Theneo-hosted developer portal at apidocs.incentivio.com that publishes no public projects, but two production Spring Boot services expose live, unauthenticated springdoc OpenAPI definitions on Incentivio's own hosts: the guest-facing Mobile & Ordering API (125 operations) and the operator-facing Admin API (421 operations), both fronted by an OAuth 2.0 authorization server advertised via RFC 8414 metadata. Narrative documentation, pricing, and self-service onboarding remain gated behind partnership and enterprise onboarding (the Connect Enterprise tier markets dedicated API SLAs).

**Areas:** Restaurant · Guest Engagement · Online Ordering · Loyalty · Customer Data Platform · Marketing Automation · Analytics · Reverse ETL · Restaurant Technology · Point-of-Sale · Gift Cards · Mobile Ordering

## Incentivio on APIs.io

Everything profiled for Incentivio is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/incentivio/](https://apis.io/providers/incentivio/)** — or go straight to one of the APIs or properties below.

### APIs (87)

- [Incentivio Connect Platform API](https://apis.io/apis/incentivio/rest-api/) — Incentivio describes an API-first, composable data platform that unifies guest data across POS, loyalty, app, web, and marketplace channels into a single…
- [Incentivio Admin Controller API](https://apis.io/apis/incentivio/incentivio-admin-controller-api/) — The admin-controller API from Incentivio — 10 operation(s) for admin-controller.
- [Incentivio App Configuration Controller API](https://apis.io/apis/incentivio/incentivio-app-configuration-controller-api/) — The app-configuration-controller API from Incentivio — 1 operation(s) for app-configuration-controller.
- [Incentivio App Content Controller API](https://apis.io/apis/incentivio/incentivio-app-content-controller-api/) — The app-content-controller API from Incentivio — 1 operation(s) for app-content-controller.
- [Incentivio App Home Config Controller API](https://apis.io/apis/incentivio/incentivio-app-home-config-controller-api/) — The app-home-config-controller API from Incentivio — 11 operation(s) for app-home-config-controller.
- [Incentivio Bulk Image Upload Controller API](https://apis.io/apis/incentivio/incentivio-bulk-image-upload-controller-api/) — The bulk-image-upload-controller API from Incentivio — 3 operation(s) for bulk-image-upload-controller.
- [Incentivio Campaign Controller API](https://apis.io/apis/incentivio/incentivio-campaign-controller-api/) — The campaign-controller API from Incentivio — 1 operation(s) for campaign-controller.
- [Incentivio Catalog Controller API](https://apis.io/apis/incentivio/incentivio-catalog-controller-api/) — The catalog-controller API from Incentivio — 7 operation(s) for catalog-controller.
- [Incentivio Client Admin Controller API](https://apis.io/apis/incentivio/incentivio-client-admin-controller-api/) — The client-admin-controller API from Incentivio — 13 operation(s) for client-admin-controller.
- [Incentivio Client Config Controller API](https://apis.io/apis/incentivio/incentivio-client-config-controller-api/) — The client-config-controller API from Incentivio — 1 operation(s) for client-config-controller.
- [Incentivio Client Configuration Controller API](https://apis.io/apis/incentivio/incentivio-client-configuration-controller-api/) — The client-configuration-controller API from Incentivio — 3 operation(s) for client-configuration-controller.
- [Incentivio Client Controller API](https://apis.io/apis/incentivio/incentivio-client-controller-api/) — The client-controller API from Incentivio — 3 operation(s) for client-controller.
- [Incentivio Client Domain Controller API](https://apis.io/apis/incentivio/incentivio-client-domain-controller-api/) — The client-domain-controller API from Incentivio — 1 operation(s) for client-domain-controller.
- [Incentivio Client Email Template Controller API](https://apis.io/apis/incentivio/incentivio-client-email-template-controller-api/) — The client-email-template-controller API from Incentivio — 6 operation(s) for client-email-template-controller.
- [Incentivio Client Merchant Controller API](https://apis.io/apis/incentivio/incentivio-client-merchant-controller-api/) — The client-merchant-controller API from Incentivio — 6 operation(s) for client-merchant-controller.
- [Incentivio Customer Report Controller API](https://apis.io/apis/incentivio/incentivio-customer-report-controller-api/) — The customer-report-controller API from Incentivio — 5 operation(s) for customer-report-controller.
- [Incentivio Customer Segment Tag Controller API](https://apis.io/apis/incentivio/incentivio-customer-segment-tag-controller-api/) — The customer-segment-tag-controller API from Incentivio — 1 operation(s) for customer-segment-tag-controller.
- [Incentivio Customer Tag And Rule Controller API](https://apis.io/apis/incentivio/incentivio-customer-tag-and-rule-controller-api/) — The customer-tag-and-rule-controller API from Incentivio — 4 operation(s) for customer-tag-and-rule-controller.
- [Incentivio Deliveries By Location Report Controller API](https://apis.io/apis/incentivio/incentivio-deliveries-by-location-report-controller-api/) — The deliveries-by-location-report-controller API from Incentivio — 1 operation(s) for deliveries-by-location-report-controller.
- [Incentivio Delivery Address Controller API](https://apis.io/apis/incentivio/incentivio-delivery-address-controller-api/) — The delivery-address-controller API from Incentivio — 3 operation(s) for delivery-address-controller.
- [Incentivio Dynamic Env Controller API](https://apis.io/apis/incentivio/incentivio-dynamic-env-controller-api/) — The dynamic-env-controller API from Incentivio — 1 operation(s) for dynamic-env-controller.
- [Incentivio Email Pulse Controller API](https://apis.io/apis/incentivio/incentivio-email-pulse-controller-api/) — The email-pulse-controller API from Incentivio — 8 operation(s) for email-pulse-controller.
- [Incentivio External Link Controller API](https://apis.io/apis/incentivio/incentivio-external-link-controller-api/) — The external-link-controller API from Incentivio — 1 operation(s) for external-link-controller.
- [Incentivio File Controller API](https://apis.io/apis/incentivio/incentivio-file-controller-api/) — The file-controller API from Incentivio — 4 operation(s) for file-controller.
- [Incentivio Fund Transfer Config Controller API](https://apis.io/apis/incentivio/incentivio-fund-transfer-config-controller-api/) — The fund-transfer-config-controller API from Incentivio — 3 operation(s) for fund-transfer-config-controller.
- [Incentivio Fund Transfer Controller API](https://apis.io/apis/incentivio/incentivio-fund-transfer-controller-api/) — The fund-transfer-controller API from Incentivio — 3 operation(s) for fund-transfer-controller.
- [Incentivio Gift Card Ach Controller API](https://apis.io/apis/incentivio/incentivio-gift-card-ach-controller-api/) — The gift-card-ach-controller API from Incentivio — 13 operation(s) for gift-card-ach-controller.
- [Incentivio Gift Card Balance Report Controller API](https://apis.io/apis/incentivio/incentivio-gift-card-balance-report-controller-api/) — The gift-card-balance-report-controller API from Incentivio — 2 operation(s) for gift-card-balance-report-controller.
- [Incentivio Gift Card Client Onboard Controller API](https://apis.io/apis/incentivio/incentivio-gift-card-client-onboard-controller-api/) — The gift-card-client-onboard-controller API from Incentivio — 6 operation(s) for gift-card-client-onboard-controller.
- [Incentivio Gift Card Controller API](https://apis.io/apis/incentivio/incentivio-gift-card-controller-api/) — The gift-card-controller API from Incentivio — 25 operation(s) for gift-card-controller.
- [Incentivio Gift Card Payment Controller API](https://apis.io/apis/incentivio/incentivio-gift-card-payment-controller-api/) — The gift-card-payment-controller API from Incentivio — 4 operation(s) for gift-card-payment-controller.
- [Incentivio Gift Card Report Controller API](https://apis.io/apis/incentivio/incentivio-gift-card-report-controller-api/) — The gift-card-report-controller API from Incentivio — 3 operation(s) for gift-card-report-controller.
- [Incentivio Group Controller API](https://apis.io/apis/incentivio/incentivio-group-controller-api/) — The group-controller API from Incentivio — 7 operation(s) for group-controller.
- [Incentivio Guest Journey Controller API](https://apis.io/apis/incentivio/incentivio-guest-journey-controller-api/) — The guest-journey-controller API from Incentivio — 6 operation(s) for guest-journey-controller.
- [Incentivio Guest Journey Report Controller API](https://apis.io/apis/incentivio/incentivio-guest-journey-report-controller-api/) — The guest-journey-report-controller API from Incentivio — 1 operation(s) for guest-journey-report-controller.
- [Incentivio Guest Order Verification Controller API](https://apis.io/apis/incentivio/incentivio-guest-order-verification-controller-api/) — The guest-order-verification-controller API from Incentivio — 2 operation(s) for guest-order-verification-controller.
- [Incentivio Home Controller API](https://apis.io/apis/incentivio/incentivio-home-controller-api/) — The home-controller API from Incentivio — 2 operation(s) for home-controller.
- [Incentivio Im Here Controller API](https://apis.io/apis/incentivio/incentivio-im-here-controller-api/) — The im-here-controller API from Incentivio — 2 operation(s) for im-here-controller.
- [Incentivio Item Controller API](https://apis.io/apis/incentivio/incentivio-item-controller-api/) — The item-controller API from Incentivio — 9 operation(s) for item-controller.
- [Incentivio Job Status Controller API](https://apis.io/apis/incentivio/incentivio-job-status-controller-api/) — The job-status-controller API from Incentivio — 1 operation(s) for job-status-controller.
- [Incentivio Location Controller API](https://apis.io/apis/incentivio/incentivio-location-controller-api/) — The location-controller API from Incentivio — 8 operation(s) for location-controller.
- [Incentivio Loyalty Controller API](https://apis.io/apis/incentivio/incentivio-loyalty-controller-api/) — The loyalty-controller API from Incentivio — 7 operation(s) for loyalty-controller.
- [Incentivio Loyalty Report Controller API](https://apis.io/apis/incentivio/incentivio-loyalty-report-controller-api/) — The loyalty-report-controller API from Incentivio — 18 operation(s) for loyalty-report-controller.
- [Incentivio Media File Controller API](https://apis.io/apis/incentivio/incentivio-media-file-controller-api/) — The media-file-controller API from Incentivio — 1 operation(s) for media-file-controller.
- [Incentivio Menu Import Controller API](https://apis.io/apis/incentivio/incentivio-menu-import-controller-api/) — The menu-import-controller API from Incentivio — 8 operation(s) for menu-import-controller.
- [Incentivio Menu Intelligence Controller API](https://apis.io/apis/incentivio/incentivio-menu-intelligence-controller-api/) — The menu-intelligence-controller API from Incentivio — 4 operation(s) for menu-intelligence-controller.
- [Incentivio Menu Search Pass Through Controller API](https://apis.io/apis/incentivio/incentivio-menu-search-pass-through-controller-api/) — The menu-search-pass-through-controller API from Incentivio — 2 operation(s) for menu-search-pass-through-controller.
- [Incentivio Merchant Controller API](https://apis.io/apis/incentivio/incentivio-merchant-controller-api/) — The merchant-controller API from Incentivio — 2 operation(s) for merchant-controller.
- [Incentivio Message Controller API](https://apis.io/apis/incentivio/incentivio-message-controller-api/) — The message-controller API from Incentivio — 5 operation(s) for message-controller.
- [Incentivio Ml Controller API](https://apis.io/apis/incentivio/incentivio-ml-controller-api/) — The ml-controller API from Incentivio — 7 operation(s) for ml-controller.
- [Incentivio Multilingual Message Controller API](https://apis.io/apis/incentivio/incentivio-multilingual-message-controller-api/) — The multilingual-message-controller API from Incentivio — 1 operation(s) for multilingual-message-controller.
- [Incentivio Offer Distribution Controller API](https://apis.io/apis/incentivio/incentivio-offer-distribution-controller-api/) — The offer-distribution-controller API from Incentivio — 2 operation(s) for offer-distribution-controller.
- [Incentivio Offers Controller API](https://apis.io/apis/incentivio/incentivio-offers-controller-api/) — The offers-controller API from Incentivio — 11 operation(s) for offers-controller.
- [Incentivio Offers Report Controller API](https://apis.io/apis/incentivio/incentivio-offers-report-controller-api/) — The offers-report-controller API from Incentivio — 2 operation(s) for offers-report-controller.
- [Incentivio Order Availability Controller API](https://apis.io/apis/incentivio/incentivio-order-availability-controller-api/) — The order-availability-controller API from Incentivio — 3 operation(s) for order-availability-controller.
- [Incentivio Order Controller API](https://apis.io/apis/incentivio/incentivio-order-controller-api/) — The order-controller API from Incentivio — 26 operation(s) for order-controller.
- [Incentivio Order Item Controller API](https://apis.io/apis/incentivio/incentivio-order-item-controller-api/) — The order-item-controller API from Incentivio — 5 operation(s) for order-item-controller.
- [Incentivio Order Offers Controller API](https://apis.io/apis/incentivio/incentivio-order-offers-controller-api/) — The order-offers-controller API from Incentivio — 5 operation(s) for order-offers-controller.
- [Incentivio Order Payment Controller API](https://apis.io/apis/incentivio/incentivio-order-payment-controller-api/) — The order-payment-controller API from Incentivio — 6 operation(s) for order-payment-controller.
- [Incentivio Package Controller API](https://apis.io/apis/incentivio/incentivio-package-controller-api/) — The package-controller API from Incentivio — 2 operation(s) for package-controller.
- [Incentivio Passwordless Auth Controller API](https://apis.io/apis/incentivio/incentivio-passwordless-auth-controller-api/) — The passwordless-auth-controller API from Incentivio — 2 operation(s) for passwordless-auth-controller.
- [Incentivio Payments Controller API](https://apis.io/apis/incentivio/incentivio-payments-controller-api/) — The payments-controller API from Incentivio — 2 operation(s) for payments-controller.
- [Incentivio Persona Controller API](https://apis.io/apis/incentivio/incentivio-persona-controller-api/) — The persona-controller API from Incentivio — 1 operation(s) for persona-controller.
- [Incentivio Preset Order Controller API](https://apis.io/apis/incentivio/incentivio-preset-order-controller-api/) — The preset-order-controller API from Incentivio — 3 operation(s) for preset-order-controller.
- [Incentivio Recaptcha Controller API](https://apis.io/apis/incentivio/incentivio-recaptcha-controller-api/) — The recaptcha-controller API from Incentivio — 1 operation(s) for recaptcha-controller.
- [Incentivio Recommendation Report Controller API](https://apis.io/apis/incentivio/incentivio-recommendation-report-controller-api/) — The recommendation-report-controller API from Incentivio — 4 operation(s) for recommendation-report-controller.
- [Incentivio Refunds Controller API](https://apis.io/apis/incentivio/incentivio-refunds-controller-api/) — The refunds-controller API from Incentivio — 2 operation(s) for refunds-controller.
- [Incentivio Report Controller API](https://apis.io/apis/incentivio/incentivio-report-controller-api/) — The report-controller API from Incentivio — 36 operation(s) for report-controller.
- [Incentivio Role Module Permission Controller API](https://apis.io/apis/incentivio/incentivio-role-module-permission-controller-api/) — The role-module-permission-controller API from Incentivio — 6 operation(s) for role-module-permission-controller.
- [Incentivio Sales Report Controller API](https://apis.io/apis/incentivio/incentivio-sales-report-controller-api/) — The sales-report-controller API from Incentivio — 4 operation(s) for sales-report-controller.
- [Incentivio Secure Signature Controller API](https://apis.io/apis/incentivio/incentivio-secure-signature-controller-api/) — The secure-signature-controller API from Incentivio — 1 operation(s) for secure-signature-controller.
- [Incentivio Segment Controller API](https://apis.io/apis/incentivio/incentivio-segment-controller-api/) — The segment-controller API from Incentivio — 5 operation(s) for segment-controller.
- [Incentivio Sms Reports Controller API](https://apis.io/apis/incentivio/incentivio-sms-reports-controller-api/) — The sms-reports-controller API from Incentivio — 4 operation(s) for sms-reports-controller.
- [Incentivio Spreedly Connector Controller API](https://apis.io/apis/incentivio/incentivio-spreedly-connector-controller-api/) — The spreedly-connector-controller API from Incentivio — 2 operation(s) for spreedly-connector-controller.
- [Incentivio Spreedly Payment Gateway Controller API](https://apis.io/apis/incentivio/incentivio-spreedly-payment-gateway-controller-api/) — The spreedly-payment-gateway-controller API from Incentivio — 2 operation(s) for spreedly-payment-gateway-controller.
- [Incentivio Store Controller API](https://apis.io/apis/incentivio/incentivio-store-controller-api/) — The store-controller API from Incentivio — 13 operation(s) for store-controller.
- [Incentivio Sub Item Controller API](https://apis.io/apis/incentivio/incentivio-sub-item-controller-api/) — The sub-item-controller API from Incentivio — 4 operation(s) for sub-item-controller.
- [Incentivio Survey Answer Controller API](https://apis.io/apis/incentivio/incentivio-survey-answer-controller-api/) — The survey-answer-controller API from Incentivio — 2 operation(s) for survey-answer-controller.
- [Incentivio Survey Controller API](https://apis.io/apis/incentivio/incentivio-survey-controller-api/) — The survey-controller API from Incentivio — 1 operation(s) for survey-controller.
- [Incentivio Tablet App Compatibility Controller API](https://apis.io/apis/incentivio/incentivio-tablet-app-compatibility-controller-api/) — The tablet-app-compatibility-controller API from Incentivio — 1 operation(s) for tablet-app-compatibility-controller.
- [Incentivio Total Controller API](https://apis.io/apis/incentivio/incentivio-total-controller-api/) — The total-controller API from Incentivio — 2 operation(s) for total-controller.
- [Incentivio Transaction Controller API](https://apis.io/apis/incentivio/incentivio-transaction-controller-api/) — The transaction-controller API from Incentivio — 2 operation(s) for transaction-controller.
- [Incentivio Transactions Controller API](https://apis.io/apis/incentivio/incentivio-transactions-controller-api/) — The transactions-controller API from Incentivio — 1 operation(s) for transactions-controller.
- [Incentivio User Controller API](https://apis.io/apis/incentivio/incentivio-user-controller-api/) — The user-controller API from Incentivio — 22 operation(s) for user-controller.
- [Incentivio Wallet Controller API](https://apis.io/apis/incentivio/incentivio-wallet-controller-api/) — The wallet-controller API from Incentivio — 3 operation(s) for wallet-controller.
- [Incentivio Web App Config Controller API](https://apis.io/apis/incentivio/incentivio-web-app-config-controller-api/) — The web-app-config-controller API from Incentivio — 1 operation(s) for web-app-config-controller.
- [Incentivio o auth 2 controller API](https://apis.io/apis/incentivio/incentivio-o-auth-2-controller-api/) — The o auth 2 controller API from Incentivio — 1 operation(s) for o auth 2 controller.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Incentivio Webhooks](https://apis.io/asyncapis/incentivio/incentivio-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Incentivio MCP server (candidate)](https://apis.io/servers/incentivio/incentivio-mcp-server-candidate/)

#### Collections (2)

Postman and Open Collection request collections.

- [OpenAPI definition](https://apis.io/collections/incentivio/open-incentivio-admin-api/)
- [OpenAPI definition](https://apis.io/collections/incentivio/open-incentivio-mobile-api/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Incentivio Admin Api Overlay](https://apis.io/overlays/incentivio/incentivio-admin-api-overlay/)
- [Incentivio Mobile Api Overlay](https://apis.io/overlays/incentivio/incentivio-mobile-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Incentivio Authentication](https://apis.io/security/incentivio/incentivio-authentication/)
- [Incentivio Domain Security](https://apis.io/security/incentivio/incentivio-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Incentivio Plans Pricing](https://apis.io/plans/incentivio/incentivio-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Incentivio Rate Limits](https://apis.io/rate-limits/incentivio/incentivio-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://incentivio.com/)
- [Documentation](https://www.incentivio.com/integrations)
- [Pricing](https://incentivio.com/demo/)
- [Support](https://incentivio.com/contact/)
- [Blog](https://incentivio.com/blog/)
- [Terms of service](https://incentivio.com/terms-of-use/)
- [Privacy policy](https://incentivio.com/privacy/)

## API Evangelist rating

**Kin Score 41.9** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 50.9 |
| Contract governance | 18.2 |
| Operational transparency | 0.0 |
| Developer ergonomics | 39.9 |
| Access clarity | 39.5 |

**Agent readiness 24.3** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly |

**Regulatory alignment 26.8** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/incentivio/](https://apis.io/providers/incentivio/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Incentivio: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/incentivio/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
