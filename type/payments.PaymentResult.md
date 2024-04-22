# Payments.PaymentResult
Payment result

```
payments.paymentResult#4e5f810d updates:Updates = payments.PaymentResult;
payments.paymentVerificationNeeded#d8411139 url:string = payments.PaymentResult;

---functions---

payments.sendPaymentForm#2d03522f flags:# form_id:long invoice:InputInvoice requested_info_id:flags.0?string shipping_option_id:flags.1?string credentials:InputPaymentCredentials tip_amount:flags.2?long = payments.PaymentResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.paymentResult | Payment result |
| payments.paymentVerificationNeeded | Payment was not successful, additional verification is needed |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.sendPaymentForm | Send compiled payment form |


