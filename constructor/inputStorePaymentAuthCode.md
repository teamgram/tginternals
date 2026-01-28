# inputStorePaymentAuthCode
Indicates payment for a login code.

```
inputStorePaymentAuthCode#9bb2636d flags:# restore:flags.0?true phone_number:string phone_code_hash:string currency:string amount:long = InputStorePaymentPurpose;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| restore | flags.0?true | Set this flag to restore a previously made purchase. |
| phone_number | string | Phone number. |
| phone_code_hash | string | phone_code_hash returned by auth.sendCode. |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Price of the product in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Type
InputStorePaymentPurpose

## Related pages
