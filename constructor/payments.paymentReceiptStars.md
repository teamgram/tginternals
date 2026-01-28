# payments.paymentReceiptStars
Receipt for payment made using Telegram Stars.

```
payments.paymentReceiptStars#dabbf83a flags:# date:int bot_id:long title:string description:string photo:flags.2?WebDocument invoice:Invoice currency:string total_amount:long transaction_id:string users:Vector<User> = payments.PaymentReceipt;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| date | int | Date of generation |
| bot_id | long | Bot ID |
| title | string | Title |
| description | string | Description |
| photo | flags.2?WebDocument | Product photo |
| invoice | Invoice | Invoice |
| currency | string | Currency, always XTR. |
| total_amount | long | Amount of Telegram Stars. |
| transaction_id | string | Transaction ID |
| users | Vector<User> | Info about users mentioned in the other fields. |


## Type
payments.PaymentReceipt

## Related pages
