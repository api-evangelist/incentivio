---
name: incentivio-place-guest-order
description: >-
  Place a pickup or delivery order at an Incentivio-powered restaurant brand —
  find a location, confirm it can take the order, build a basket, price it, and
  take payment.
api: incentivio:mobile-api
base_url: https://mobile.incentivio.com/incentivio-mobile-api
generated: '2026-08-13'
method: generated
source: >-
  openapi/incentivio-mobile-api-openapi.yml (operationIds verified against the
  spec), conventions/incentivio-conventions.yml,
  errors/incentivio-error-codes.yml
operations:
  - getClientIdByAlias
  - findLocations
  - getLocation
  - newGetOrderAvailability
  - calculateAsapDuration
  - isWithinDeliveryRadius
  - listCatalogs
  - retrieveCachedCatalogs
  - viewItemById
  - getOutOfStockItemIdsByLocation
  - addOrUpdateOrder
  - addOrderItem
  - addOrderItemList
  - updateOrderItem
  - deleteOrderItem
  - getOrderItemPrice
  - calculatePrice
  - calculateOrderTotalForItems
  - listPaymentInstruments
  - prepareOrderPayment
  - makeOrderPayment
  - prepareGuestOrderPayment
  - makeGuestOrderPayment
  - checkOrderPaymentStatus
  - viewOrderById
---

# Place a guest order

Incentivio's ordering API is multi-tenant. Nothing works until you know which
restaurant brand you are acting for, and everything fails unhelpfully if you get
that wrong.

## Before you start

1. **Resolve the tenant.** Every call takes a `CLIENTID` header. If you only have
   a brand alias, call `getClientIdByAlias` (`GET /clientalias/{clientAlias}`) to
   turn it into the id the rest of the API expects.
2. **Get a token.** All ordering operations require `Authorization: Bearer <token>`.
   Unauthenticated calls return `401` with `WWW-Authenticate: Bearer realm="restservice"`.
   The authorization server metadata is published at
   `/.well-known/oauth-authorization-server` (issuer `https://order.incentivio.com/issuer`).
   Guest checkout is possible on the payment path (`prepareGuestOrderPayment`,
   `makeGuestOrderPayment`) but the rest of the flow still needs a token.
3. **Read errors off the headers, not the body.** Error bodies are EMPTY. The
   reason is in `incentivio-code` and `incentivio-message`. Capture `trace-id`
   from every response — it is the only thing support can act on.

## Steps

### 1. Find a location
`findLocations` (`GET /locations`) lists the brand's locations;
`getLocation` (`GET /locationsdetail/{locationid}`) returns hours, address and
order value limits for one of them.

### 2. Confirm the location can take this order
`newGetOrderAvailability` (`POST /locations/{locationid}/orderavailability`)
returns available fulfilment types and time slots. For an ASAP order use
`calculateAsapDuration` (`POST /locations/{locationid}/orderavailability/asap`)
to get the promised wait. For delivery, check the address first with
`isWithinDeliveryRadius` (`GET /locations/{locationid}/withindeliveryradius`) —
doing this after the basket is built wastes the guest's time.

### 3. Load the menu
`listCatalogs` (`GET /catalogs`), or `retrieveCachedCatalogs`
(`GET /cachedcatalogs`) / `getCompressedCachedCatalog`
(`GET /cachedcatalogs/compressed`) when you want the cached form. Pull item detail
with `viewItemById` (`GET /items/{itemid}`). Always call
`getOutOfStockItemIdsByLocation` (`GET /items/outofstock/{locationId}`) before
offering items — the catalog is brand-wide, availability is per location.

### 4. Build the order
`addOrUpdateOrder` (`PUT /orders`) creates or updates the order. Add lines with
`addOrderItem` (`PUT /orders/{orderid}/orderitems`) or `addOrderItemList`
(`PUT /orders/{orderid}/addorderitems`), change them with `updateOrderItem`, and
remove them with `deleteOrderItem`
(`DELETE /orders/{orderid}/orderitems/{orderitemid}`).

These are `PUT` operations, so a repeated call is safe by HTTP semantics. That is
the only replay protection this API offers — there is no idempotency key
anywhere.

### 5. Price it
`getOrderItemPrice` (`POST /orders/{orderid}/orderitemprice`) prices a single
line. `calculatePrice` (`GET /orders/{orderid}/calculatetotal`) totals the order
with taxes and charges. To quote a basket before an order exists, use
`calculateOrderTotalForItems` (`POST /locations/{locationid}/calculatetotal`).

Never compute the total yourself. Taxes and charges are location-specific and
come back in `TaxSummary` and `ChargeSummary`.

### 6. Take payment

**Read this before calling anything in this step.** `makeOrderPayment` is a POST
with no idempotency key. If it times out you cannot safely retry it. Instead:

1. `listPaymentInstruments` (`GET /paymentinstruments`) for a signed-in guest, or
   collect a new instrument with `addPaymentInstrument`.
2. `prepareOrderPayment` (`POST /orders/{orderid}/preparepayment`) — or
   `prepareGuestOrderPayment` for guest checkout.
3. `makeOrderPayment` (`POST /orders/{orderid}/makepayment`) — or
   `makeGuestOrderPayment`.
4. On ANY ambiguous result — timeout, 500, connection reset — do **not** call
   `makeOrderPayment` again. Call `checkOrderPaymentStatus`
   (`GET /orders/{orderid}/paymentstatus`) and act on what it says.

### 7. Confirm
`viewOrderById` (`GET /orders/{orderid}`) returns the final order. For dine-in or
curbside, `markAnOrderImHere` (`POST /users/{userId}/orders/markimhere`) tells the
kitchen the guest has arrived.

## Failure modes you will actually hit

| What you see | What it means | What to do |
|---|---|---|
| `400` / `incentivio-code: BAD_REQUEST` | Missing `CLIENTID`, or a required parameter absent. The response does not say which one. | Re-check the tenant header first — it is the usual cause. |
| `401` / `Full authentication is required to access this resource` | No token, or token rejected. | Re-authenticate. |
| `500` / `incentivio-code: ERROR` | Frequently a tenant-resolution failure surfacing as a server error on read endpoints like `/locations` and `/stores`. | Retry once with a valid `CLIENTID`; capture `trace-id`. |
| Empty response body on an error | Expected. This API never returns an error object. | Read `incentivio-code` / `incentivio-message`. |
