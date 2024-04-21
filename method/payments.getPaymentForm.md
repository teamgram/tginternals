# payments.getPaymentForm
Get a payment form

```
payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;
---functions---
payments.getPaymentForm#37148dbb flags:# invoice:InputInvoice theme_params:flags.0?DataJSON = payments.PaymentForm;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| invoice | InputInvoice | Invoice |
| theme_params | flags.0?DataJSON | A JSON object with the following keys, containing color theme information (integers, RGB24) to pass to the payment provider, to apply in eventual verification pages: bg_color - Background color text_color - Text color hint_color - Hint text color link_color - Link color button_color - Button color button_text_color - Button text color |


## Result
payments.PaymentForm

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOOST_PEER_INVALID | The specified boost_peer is invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | SLUG_INVALID | The specified invoice slug is invalid. |
| 400 | UNTIL_DATE_INVALID | Invalid until date provided. |

