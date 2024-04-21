# updateBotPrecheckoutQuery
This object contains information about an incoming pre-checkout query.

```
updateBotPrecheckoutQuery#8caa9a96 flags:# query_id:long user_id:long payload:bytes info:flags.0?PaymentRequestedInfo shipping_option_id:flags.1?string currency:string total_amount:long = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query_id | long | Unique query identifier |
| user_id | long | User who sent the query |
| payload | bytes | Bot specified invoice payload |
| info | flags.0?PaymentRequestedInfo | Order info provided by the user |
| shipping_option_id | flags.1?string | Identifier of the shipping option chosen by the user |
| currency | string | Three-letter ISO 4217 currency code |
| total_amount | long | Total amount in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Type
Update

## Related pages
