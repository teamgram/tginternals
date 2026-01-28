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
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | CURRENCY_TOTAL_AMOUNT_INVALID | The total amount of all prices is invalid. |
| 400 | INVOICE_PAYLOAD_INVALID | The specified invoice payload is invalid. |
| 400 | MEDIA_INVALID | Media invalid. |
| 400 | PAYMENT_PROVIDER_INVALID | The specified payment provider is invalid. |
| 400 | STARS_INVOICE_INVALID | The specified Telegram Star invoice is invalid. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |
| 400 | WEBDOCUMENT_MIME_INVALID | Invalid webdocument mime type provided. |
| 400 | WEBDOCUMENT_URL_EMPTY | The passed web document URL is empty. |

