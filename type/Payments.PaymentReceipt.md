# Payments.PaymentReceipt
Payment receipt

```
payments.paymentReceipt#70c4fe03 flags:# date:int bot_id:long provider_id:long title:string description:string photo:flags.2?WebDocument invoice:Invoice info:flags.0?PaymentRequestedInfo shipping:flags.1?ShippingOption tip_amount:flags.3?long currency:string total_amount:long credentials_title:string users:Vector<User> = payments.PaymentReceipt;

---functions---

payments.getPaymentReceipt#2478d1cc peer:InputPeer msg_id:int = payments.PaymentReceipt;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.paymentReceipt | Receipt |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getPaymentReceipt | Get payment receipt |


