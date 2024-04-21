# messageActionPaymentSent
A payment was sent

```
messageActionPaymentSent#96163f56 flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long invoice_slug:flags.0?string = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| recurring_init | flags.2?true | Whether this is the first payment of a recurring payment we just subscribed to |
| recurring_used | flags.3?true | Whether this payment is part of a recurring payment |
| currency | string | Three-letter ISO 4217 currency code |
| total_amount | long | Price of the product in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| invoice_slug | flags.0?string | An invoice slug taken from an invoice deep link or from the premium_invoice_slug app config parameter » |


## Type
MessageAction

## Related pages
