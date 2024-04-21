# messageActionPaymentSentMe
A user just sent a payment to me (a bot)

```
messageActionPaymentSentMe#8f31b327 flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long payload:bytes info:flags.0?PaymentRequestedInfo shipping_option_id:flags.1?string charge:PaymentCharge = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| recurring_init | flags.2?true | Whether this is the first payment of a recurring payment we just subscribed to |
| recurring_used | flags.3?true | Whether this payment is part of a recurring payment |
| currency | string | Three-letter ISO 4217 currency code |
| total_amount | long | Price of the product in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| payload | bytes | Bot specified invoice payload |
| info | flags.0?PaymentRequestedInfo | Order info provided by the user |
| shipping_option_id | flags.1?string | Identifier of the shipping option chosen by the user |
| charge | PaymentCharge | Provider payment identifier |


## Type
MessageAction

## Related pages
