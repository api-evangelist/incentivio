---
name: incentivio-loyalty-and-offers
description: >-
  Read a guest's Incentivio loyalty balance and expiring points, find the offers
  distributed to them, and apply or redeem an offer against an order.
api: incentivio:mobile-api
base_url: https://mobile.incentivio.com/incentivio-mobile-api
generated: '2026-08-13'
method: generated
source: >-
  openapi/incentivio-mobile-api-openapi.yml (operationIds verified against the
  spec), conventions/incentivio-conventions.yml
operations:
  - viewLoyaltyAccount
  - findLoyaltyPointsSummary
  - viewLoyalAccountHistory
  - getExpiringLoyaltyPoints
  - getNextExpiringLoyaltyPoints
  - upsertLoyaltyAccountExternalId
  - upsertLoyaltyCardId
  - findDistributedOffers
  - getOffer
  - getDistributedOffer
  - getOffersBasedOnUserActivity
  - getActivityBasedContent
  - updateDistributedOfferStatus
  - redeemById
  - processQRCode
  - applyDiscount
  - removeDiscount
  - disableNextVisitOffers
  - findTransactions
---

# Loyalty and offers

Loyalty in Incentivio is keyed by the guest **and** the brand — there is no
global loyalty balance. Every call needs both a bearer token (which identifies
the guest) and a `CLIENTID` header (which identifies the brand).

## Reading the loyalty position

- `viewLoyaltyAccount` (`GET /loyaltyaccounts`) — the account itself.
- `findLoyaltyPointsSummary` (`GET /loyaltypointssummary`) — the balance summary.
- `viewLoyalAccountHistory` (`GET /loyaltyaccounts/accounthistory`) — earn and
  burn history. Paginate with `page` and `count`.
- `getNextExpiringLoyaltyPoints` (`GET /loyaltyaccounts/next-expiring-points`) and
  `getExpiringLoyaltyPoints` (`GET /loyaltyaccounts/expiring-points`).

If you are answering "should I tell this guest anything?", the expiring-points
endpoints are the ones that carry urgency. Lead with them.

## Linking an external loyalty identity

When a brand runs loyalty in a POS or a third-party program, attach their key to
the Incentivio account:

- `upsertLoyaltyAccountExternalId` (`PUT /loyaltyaccounts`)
- `upsertLoyaltyCardId` (`PUT /loyaltyaccounts/loyaltycard`)

Both are `PUT` upserts, so re-running them is safe.

## Finding offers

- `findDistributedOffers` (`GET /appoffers`) — the offers actually issued to this
  guest. This is the list to show. A distributed offer carries a
  `distributedOfferId`, which is what redemption operates on.
- `getDistributedOffer` (`GET /distributedoffers/{distributedofferid}`) — detail
  for one.
- `getOffer` (`GET /offers/{offerid}`) — the underlying offer definition.
- `getOffersBasedOnUserActivity` (`POST /getactivitybasedoffers`) and
  `getActivityBasedContent` (`POST /getactivitybasedcontent`) — behaviourally
  targeted offers and content.

Do not present an offer from `getOffer` as available to a guest. Only a
distributed offer is theirs.

## Redeeming

Against an order:

1. `applyDiscount` (`POST /orders/{orderid}/applydiscount`) with the
   `distributedOfferId`.
2. Re-price with `calculatePrice` (`GET /orders/{orderid}/calculatetotal`) — never
   assume the discount amount.
3. `removeDiscount` (`POST /orders/{orderid}/removediscount`) to back it out.

Outside an order:

- `redeemById` (`POST /redeemofferbyid`) — direct redemption.
- `processQRCode` (`POST /processqrcode`) — in-store scan redemption.
- `updateDistributedOfferStatus` (`POST /changedistributedofferstatus`) — move an
  offer's status without redeeming it.
- `disableNextVisitOffers` (`GET /orderoffers/disablenextvisitoffers`) — suppress
  next-visit offer generation.

## Verifying what happened

`findTransactions` (`GET /transactions`) is the ledger. Because errors carry no
body and no operation is idempotent, a redemption whose response you did not see
should be confirmed here rather than retried — a repeated `redeemById` can burn
the offer twice.

## Conventions that apply throughout

- Pagination: `page` and `count`; sorting: `sortby` and `sortdirection`.
- Language: pass `langCode` / `languageCode` or the `inc-user-language` header.
  Offer and message copy is multilingual.
- Errors: empty body, `incentivio-code` / `incentivio-message` headers. See
  `errors/incentivio-error-codes.yml`.
