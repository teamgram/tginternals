# messageActionPaymentRefunded
Describes a payment refund (service message received by both users and bots).

```
messageActionPaymentRefunded#41b3e202 flags:# peer:Peer currency:string total_amount:long payload:flags.0?bytes charge:PaymentCharge = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | Peer | Identifier of the peer that returned the funds. |
| currency | string | Currency, XTR for Telegram Stars. |
| total_amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| payload | flags.0?bytes | Bot specified invoice payload (only received by bots). |
| charge | PaymentCharge | Provider payment identifier |


## Type
MessageAction

## Related pages
