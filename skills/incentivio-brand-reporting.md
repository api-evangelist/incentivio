---
name: incentivio-brand-reporting
description: >-
  Pull sales, order, loyalty, offer and customer reports for a restaurant brand
  from the Incentivio Admin API, including CSV exports.
api: incentivio:admin-api
base_url: https://adminapi.incentivio.com/incentivio-admin-api
generated: '2026-08-13'
method: generated
source: >-
  openapi/incentivio-admin-api-openapi.yml (operationIds verified against the
  spec), conventions/incentivio-conventions.yml
operations:
  - getSalesByLocationReport
  - getSalesByChannelReport
  - getSalesByChannelOverTimeReport
  - getSalesByOrderTypeReport
  - retrieveSalesByPosCategoryReport
  - retrieveSalesByOrderSourceReport
  - retrieveSalesByLocationReport
  - retrieveSalesByLocationForPreviousMonthReport
  - getOrdersByLocationReport
  - getOrdersByChannelReport
  - getOrdersByOrderTypeReport
  - getOrdersBySignInStatusReport
  - getAverageOrderSizeReport
  - getMostPopularItemsReport
  - getLeastPopularItemsReport
  - getFrequentlyBoughtTogetherReport
  - getDailyActiveUsersReport
  - getMonthlyActiveUsersReport
  - retrieveNewSignUps
  - retrieveTotalSignUps
  - customersDownload
  - downloadActiveCustomers
  - getCustomersByLoyaltyBalanceReport
  - getCustomersByDaysSinceLastPurchaseReport
  - getCustomersByAverageBasketValueReport
  - getOfferPerformanceReport
  - retrieveOfferPerformanceReport
  - exportOfferPerformanceReport
  - getLoyaltyReportSummaryForBrand
  - getLoyaltyReportPointsSummaryForBrand
  - getLoyaltyReportOrdersForBrand
  - getLoyaltyReportSignUpTimeseriesForBrand
  - getLoyaltyReportLocationPerformancePage
  - getLoyaltyReportOfferPerformanceData
  - getLoyaltyReportLocationPerformanceCSV
  - getLoyaltyReportOfferPerformanceCSV
  - getSurveyReport
  - getGiftCardPoolSummaryReport
  - downloadGiftCardPoolSummaryAsCSVS3Url
---

# Brand reporting

The Incentivio Admin API carries roughly 60 report endpoints under
`/incentivio-reports/`. They divide into three families that do not share a shape,
so pick the family first.

## Before you start

- Authenticate against the **admin** authorization server
  (`https://admin.incentivio.com/issuer`) — it is a different issuer from the
  guest one. An unauthenticated call returns `401` with `incentivio-code: Unknown`
  and no `WWW-Authenticate` header.
- Scope the request: `Inc-Client-Id` header, or a `clientid`/`clientId` path
  parameter depending on the endpoint. Both spellings exist. Some endpoints also
  take `Inc-Merchant-Id`.
- Nearly every report takes `startdate`/`enddate` (or `startDate`/`endDate`, or
  `dateRange`) plus `storeIds`/`storeids`. The casing is inconsistent per
  endpoint — read the operation in the spec rather than assuming.

## Family 1 — classic client reports (`/incentivio-reports/clients/{clientid}/...`)

Sales and orders:
`getSalesByLocationReport`, `getSalesByChannelReport`,
`getSalesByChannelOverTimeReport`, `getSalesByOrderTypeReport`,
`getOrdersByLocationReport`, `getOrdersByChannelReport`,
`getOrdersByOrderTypeReport`, `getOrdersBySignInStatusReport`,
`getAverageOrderSizeReport`.

Menu performance:
`getMostPopularItemsReport`, `getLeastPopularItemsReport`,
`getFrequentlyBoughtTogetherReport`.

Guests:
`getDailyActiveUsersReport`, `getMonthlyActiveUsersReport`,
`getCustomersByLoyaltyBalanceReport`,
`getCustomersByDaysSinceLastPurchaseReport`,
`getCustomersByAverageBasketValueReport`, `getCustomersByOrdersReport`,
`getCustomersByAgeReport`, `getCustomersByGenderReport`.

Marketing:
`getOfferPerformanceReport`, `getMessagePerformanceReport`,
`getOfferRedemptionByTimeOfTheDayReport`, `getSurveyReport`.

## Family 2 — newer client reports (`/incentivio-reports/clients/{clientId}/...`)

`retrieveSalesByLocationReport`, `retrieveSalesByPosCategoryReport`,
`retrieveSalesByOrderSourceReport`, `retrieveNewSignUps`, `retrieveTotalSignUps`,
`retrieveOfferPerformanceReport`, plus previous-month variants
(`retrieveSalesByLocationForPreviousMonthReport`,
`retrieveNewSignUpsForPreviousMonth`).

Note this family overlaps the first — there are two sales-by-location reports
under two different operationIds and two different path casings. Decide which one
your brand's console uses and stay on it; do not mix results from both in one
number.

## Family 3 — loyalty reports (`/incentivio-reports/loyaltyreport/...`)

Brand level: `getLoyaltyReportSummaryForBrand`,
`getLoyaltyReportPointsSummaryForBrand`, `getLoyaltyReportOrdersForBrand`,
`getLoyaltyReportSignUpTimeseriesForBrand`.

Franchise level: `getLoyaltyReportFranchiseSummary`,
`getLoyaltyReportLoyaltySalesForFranchise`,
`getLoyaltyReportSignUpTimeseriesForFranchise`.

Location and offer level: `getLoyaltyReportLocationPerformancePage`,
`getLoyaltyReportLocationsTrendsPage`, `getLoyaltyReportOfferPerformanceData`,
`getLoyaltyReportOffersTrendsPage`, each with a `.../summary` companion.

## Exports

Several reports have a CSV sibling, and these are `POST` even though they read:

- `getLoyaltyReportLocationPerformanceCSV`, `getLoyaltyReportLocationTrendsCSV`,
  `getLoyaltyReportOfferPerformanceCSV`, `getLoyaltyReportOfferTrendsCSV`
- `exportOfferPerformanceReport`, `downloadActiveCustomers`, `customersDownload`
- `downloadGiftCardPoolSummaryAsCSV2` (direct `text/csv`) and
  `downloadGiftCardPoolSummaryAsCSVS3Url` (returns a signed S3 URL instead)

Prefer the S3-URL variant for large exports. Treat any returned S3 URL as a
short-lived secret: it grants read access to brand customer data with no further
authentication.

## Cautions

- **Customer downloads are PII.** `customersDownload` and `downloadActiveCustomers`
  return guest-level records. Do not hand them to a general-purpose agent context,
  and do not persist them outside the brand's own systems.
- **Pagination** is `page` + `count`; sorting is `sortby` + `sortDirection` here
  (capital D, unlike the mobile API).
- **Media types are unreliable.** 304 of the 421 admin operations declare `*/*`
  rather than a concrete content type. Inspect the actual `content-type` on the
  response.
- **No 4xx or 5xx responses are declared** anywhere in the definition. Handle
  failures from `incentivio-code` / `incentivio-message` headers with an empty
  body.
