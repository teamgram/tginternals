# payments.getPaymentForm
Get a payment form

```
payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;
payments.paymentFormStars#7bf6b15c flags:# form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice users:Vector<User> = payments.PaymentForm;
payments.paymentFormStarGift#b425cfe1 form_id:long invoice:Invoice = payments.PaymentForm;
---functions---
payments.getPaymentForm#37148dbb flags:# invoice:InputInvoice theme_params:flags.0?DataJSON = payments.PaymentForm;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| invoice | InputInvoice | Invoice |
| theme_params | flags.0?DataJSON | Theme parameters » |


## Result
payments.PaymentForm

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 406 | API_GIFT_RESTRICTED_UPDATE_APP | Please update the app to access the gift API. |
| 400 | BOOST_PEER_INVALID | The specified boost_peer is invalid. |
| 403 | BOT_ACCESS_FORBIDDEN | The specified method can be used over a business connection for some operations, but the specified query attempted an operation that is not allowed over a business connection. |
| 400 | BOT_INVOICE_INVALID | The specified invoice is invalid. |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | GIFT_MONTHS_INVALID | The value passed in invoice.inputInvoicePremiumGiftStars.months is invalid. |
| 400 | INVOICE_INVALID | The specified invoice is invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MONTH_INVALID | The number of months specified in inputInvoicePremiumGiftStars.months is invalid. |
| 400 | NO_PAYMENT_NEEDED | The upgrade/transfer of the specified gift was already paid for or is free. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | SLUG_INVALID | The specified invoice slug is invalid. |
| 400 | STARGIFT_ALREADY_CONVERTED | The specified star gift was already converted to Stars. |
| 400 | STARGIFT_ALREADY_REFUNDED | The specified star gift was already refunded. |
| 400 | STARGIFT_ALREADY_UPGRADED | The specified gift was already upgraded to a collectible gift. |
| 406 | STARGIFT_EXPORT_IN_PROGRESS | A gift export is in progress, a detailed and localized description for the error will be emitted via an updateServiceNotification as specified here ». |
| 400 | STARGIFT_INVALID | The passed gift is invalid. |
| 400 | STARGIFT_NOT_FOUND | The specified gift was not found. |
| 400 | STARGIFT_OWNER_INVALID | You cannot transfer or sell a gift owned by another user. |
| 400 | STARGIFT_PEER_INVALID | The specified inputSavedStarGiftChat.peer is invalid. |
| 400 | STARGIFT_RESELL_CURRENCY_NOT_ALLOWED | You can't buy the gift using the specified currency (i.e. trying to pay in Stars for TON gifts). |
| 400 | STARGIFT_SLUG_INVALID | The specified gift slug is invalid. |
| 400 | STARGIFT_TRANSFER_TOO_EARLY_%d | You cannot transfer this gift yet, wait %d seconds. |
| 400 | STARGIFT_UPGRADE_UNAVAILABLE | A received gift can only be upgraded to a collectible gift if the messageActionStarGift/savedStarGift.can_upgrade flag is set. |
| 406 | STARS_FORM_AMOUNT_MISMATCH | The form amount has changed, please fetch the new form using payments.getPaymentForm and restart the process. |
| 400 | TO_ID_INVALID | The specified to_id of the passed inputInvoiceStarGiftResale or inputInvoiceStarGiftTransfer is invalid. |
| 400 | UNTIL_DATE_INVALID | Invalid until date provided. |

