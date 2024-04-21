# payments.sendPaymentForm
Send compiled payment form

```
payments.paymentResult#4e5f810d updates:Updates = payments.PaymentResult;
payments.paymentVerificationNeeded#d8411139 url:string = payments.PaymentResult;
---functions---
payments.sendPaymentForm#2d03522f flags:# form_id:long invoice:InputInvoice requested_info_id:flags.0?string shipping_option_id:flags.1?string credentials:InputPaymentCredentials tip_amount:flags.2?long = payments.PaymentResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| form_id | long | Form ID |
| invoice | InputInvoice | Invoice |
| requested_info_id | flags.0?string | ID of saved and validated order info |
| shipping_option_id | flags.1?string | Chosen shipping option ID |
| credentials | InputPaymentCredentials | Payment credentials |
| tip_amount | flags.2?long | Tip, in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Result
payments.PaymentResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |

