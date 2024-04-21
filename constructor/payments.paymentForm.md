# payments.paymentForm
Payment form

```
payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| can_save_credentials | flags.2?true | Whether the user can choose to save credentials. |
| password_missing | flags.3?true | Indicates that the user can save payment credentials, but only after setting up a 2FA password (currently the account doesn't have a 2FA password) |
| form_id | long | Form ID |
| bot_id | long | Bot ID |
| title | string | Form title |
| description | string | Description |
| photo | flags.5?WebDocument | Product photo |
| invoice | Invoice | Invoice |
| provider_id | long | Payment provider ID. |
| url | string | Payment form URL |
| native_provider | flags.4?string | Payment provider name.One of the following:- stripe |
| native_params | flags.4?DataJSON | Contains information about the payment provider, if available, to support it natively without the need for opening the URL.A JSON object that can contain the following fields:- apple_pay_merchant_id: Apple Pay merchant ID- google_pay_public_key: Google Pay public key- need_country: True, if the user country must be provided,- need_zip: True, if the user ZIP/postal code must be provided,- need_cardholder_name: True, if the cardholder name must be provided |
| additional_methods | flags.6?Vector<PaymentFormMethod> | Additional payment methods |
| saved_info | flags.0?PaymentRequestedInfo | Saved server-side order information |
| saved_credentials | flags.1?Vector<PaymentSavedCredentials> | Contains information about saved card credentials |
| users | Vector<User> | Users |


## Type
payments.PaymentForm

## Related pages
