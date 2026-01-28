# payments.paymentFormStars
Represents a payment form, for payments to be using Telegram Stars, see here » for more info.

```
payments.paymentFormStars#7bf6b15c flags:# form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice users:Vector<User> = payments.PaymentForm;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| form_id | long | Form ID. |
| bot_id | long | Bot ID. |
| title | string | Form title |
| description | string | Description |
| photo | flags.5?WebDocument | Product photo |
| invoice | Invoice | Invoice |
| users | Vector<User> | Info about users mentioned in the other fields. |


## Type
payments.PaymentForm

## Related pages
