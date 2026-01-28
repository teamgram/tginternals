# Payments.PaymentForm
Payment form

```
payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;
payments.paymentFormStars#7bf6b15c flags:# form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice users:Vector<User> = payments.PaymentForm;
payments.paymentFormStarGift#b425cfe1 form_id:long invoice:Invoice = payments.PaymentForm;

---functions---

payments.getPaymentForm#37148dbb flags:# invoice:InputInvoice theme_params:flags.0?DataJSON = payments.PaymentForm;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.paymentForm | Payment form |
| payments.paymentFormStars | Represents a payment form, for payments to be using Telegram Stars, see here » for more info. |
| payments.paymentFormStarGift | Represents a payment form for a gift, see here » for more info. |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getPaymentForm | Get a payment form |


