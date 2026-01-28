# payments.sendStarsForm
Make a payment using Telegram Stars, see here » for more info.

```
payments.paymentResult#4e5f810d updates:Updates = payments.PaymentResult;
payments.paymentVerificationNeeded#d8411139 url:string = payments.PaymentResult;
---functions---
payments.sendStarsForm#7998c914 form_id:long invoice:InputInvoice = payments.PaymentResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| form_id | long | Payment form ID |
| invoice | InputInvoice | Invoice |


## Result
payments.PaymentResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 406 | API_GIFT_RESTRICTED_UPDATE_APP | Please update the app to access the gift API. |
| 400 | BALANCE_TOO_LOW | The transaction cannot be completed because the current Telegram Stars balance is too low. |
| 403 | BOT_ACCESS_FORBIDDEN | The specified method can be used over a business connection for some operations, but the specified query attempted an operation that is not allowed over a business connection. |
| 400 | BOT_INVOICE_INVALID | The specified invoice is invalid. |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | FORM_EXPIRED | The form was generated more than 10 minutes ago and has expired, please re-generate it using payments.getPaymentForm and pass the new form_id. |
| 400 | FORM_ID_EMPTY | The specified form ID is empty. |
| 400 | FORM_SUBMIT_DUPLICATE | The same payment form was already submitted.  . |
| 400 | FORM_UNSUPPORTED | Please update your client. |
| 400 | GIFT_STARS_INVALID | The specified amount of stars is invalid. |
| 400 | MEDIA_ALREADY_PAID | You already paid for the specified media. |
| 400 | MONTH_INVALID | The number of months specified in inputInvoicePremiumGiftStars.months is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 406 | PRECHECKOUT_FAILED | Precheckout failed, a detailed and localized description for the error will be emitted via an updateServiceNotification as specified here ». |
| 400 | PURPOSE_INVALID | The specified payment purpose is invalid. |
| 400 | STARGIFT_ALREADY_UPGRADED | The specified gift was already upgraded to a collectible gift. |
| 400 | STARGIFT_NOT_FOUND | The specified gift was not found. |
| 400 | STARGIFT_OWNER_INVALID | You cannot transfer or sell a gift owned by another user. |
| 400 | STARGIFT_SLUG_INVALID | The specified gift slug is invalid. |
| 400 | STARGIFT_USAGE_LIMITED | The gift is sold out. |
| 400 | STARGIFT_USER_USAGE_LIMITED | You've reached the starGift.limited_per_user limit, you can't buy any more gifts of this type. |
| 406 | STARS_FORM_AMOUNT_MISMATCH | The form amount has changed, please fetch the new form using payments.getPaymentForm and restart the process. |
| 400 | TO_ID_INVALID | The specified to_id of the passed inputInvoiceStarGiftResale or inputInvoiceStarGiftTransfer is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

