---
name: incentivio-gift-cards
description: >-
  Buy, gift, reload and look up Incentivio stored-value gift cards, and attach an
  existing card as a payment instrument.
api: incentivio:mobile-api
base_url: https://mobile.incentivio.com/incentivio-mobile-api
generated: '2026-08-13'
method: generated
source: >-
  openapi/incentivio-mobile-api-openapi.yml (operationIds verified against the
  spec), errors/incentivio-error-codes.yml
operations:
  - myGiftCard
  - cardLookupByNumber
  - cardLookupByToken
  - secureCardLookupByToken
  - purchaseECard
  - purchaseECardPreparePayment
  - purchaseAndEmailGiftCard
  - purchaseAndEmailGiftCardPreparePayment
  - addValuetoGiftCard
  - addValueToGiftCardPreparePayment
  - addExistingGiftCard
  - checkTxPaymentStatus
  - listPaymentInstruments
  - addPaymentInstrument
---

# Gift cards

Every operation here moves money. The Incentivio API has **no idempotency
support**, so the discipline below is not optional — it is the only thing
standing between a dropped connection and a double charge.

## The two-step payment pattern

Gift card purchase and reload are always prepare-then-execute:

| Flow | Prepare | Execute |
|---|---|---|
| Buy an e-card for yourself | `purchaseECardPreparePayment` (`POST /ecard/purchase/payment/prepare`) | `purchaseECard` (`POST /purchase/ecard`) |
| Buy and email a card to someone | `purchaseAndEmailGiftCardPreparePayment` (`POST /giftcard/purchase/payment/prepare`) | `purchaseAndEmailGiftCard` (`POST /giftcard/purchase`) |
| Reload an existing card | `addValueToGiftCardPreparePayment` (`POST /giftcard/add-value/payment/prepare`) | `addValuetoGiftCard` (`POST /giftcard/add-value`) |

**If an execute call returns anything ambiguous — a timeout, a 500, a reset — do
not repeat it.** Take the Incentivio transaction id and call
`checkTxPaymentStatus` (`GET /giftcard/transaction/{incentiviotxid}/payment/status`).
That endpoint exists precisely because there is no idempotency key.

## Looking cards up

- `myGiftCard` (`GET /mygiftcard`) — the signed-in guest's cards.
- `cardLookupByNumber` (`POST /giftcard/lookup`) — by card number, for balance checks.
- `cardLookupByToken` (`GET /giftcard/tokenlookup/{token}`) and
  `secureCardLookupByToken` (`GET /giftcard/securetokenlookup/{token}`) — by
  token. Prefer the secure variant; treat both tokens as bearer secrets and never
  log them.

## Using a card to pay

`addExistingGiftCard` (`POST /giftcard/paymentinstruments`) attaches a card as a
payment instrument. After that it appears in `listPaymentInstruments`
(`GET /paymentinstruments`) and can be used through the normal order payment flow
(`prepareOrderPayment` then `makeOrderPayment`).

## Handling the guest

- Balances and card numbers are sensitive. Incentivio publishes a gift card fraud
  consumer notice at https://incentivio.com/gift-card-fraud-consumer-notice/ —
  never read a full card number back to an unverified caller, and never accept a
  card number over an unauthenticated channel.
- All operations are brand-scoped: pass `CLIENTID`. A card issued by one brand is
  not valid at another.
- Errors return an empty body. Read `incentivio-code` and `incentivio-message`
  from the response headers and record `trace-id` for any payment dispute.
