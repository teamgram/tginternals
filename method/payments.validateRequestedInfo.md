# payments.validateRequestedInfo
Submit requested order information for validation

```
payments.validatedRequestedInfo#d1451883 flags:# id:flags.0?string shipping_options:flags.1?Vector<ShippingOption> = payments.ValidatedRequestedInfo;
---functions---
payments.validateRequestedInfo#b6c8f12b flags:# save:flags.0?true invoice:InputInvoice info:PaymentRequestedInfo = payments.ValidatedRequestedInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| save | flags.0?true | Save order information to re-use it for future orders |
| invoice | InputInvoice | Invoice |
| info | PaymentRequestedInfo | Requested order information |


## Result
payments.ValidatedRequestedInfo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |

