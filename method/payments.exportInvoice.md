# payments.exportInvoice
Generate an invoice deep link

```
payments.exportedInvoice#aed0cbd9 url:string = payments.ExportedInvoice;
---functions---
payments.exportInvoice#f91b065 invoice_media:InputMedia = payments.ExportedInvoice;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| invoice_media | InputMedia | Invoice |


## Result
payments.ExportedInvoice

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CURRENCY_TOTAL_AMOUNT_INVALID | The total amount of all prices is invalid. |
| 400 | INVOICE_PAYLOAD_INVALID | The specified invoice payload is invalid. |
| 400 | MEDIA_INVALID | Media invalid. |
| 400 | PAYMENT_PROVIDER_INVALID | The specified payment provider is invalid. |

