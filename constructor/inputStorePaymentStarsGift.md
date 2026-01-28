# inputStorePaymentStarsGift
Used to gift Telegram Stars to a friend.

```
inputStorePaymentStarsGift#1d741ef7 user_id:InputUser stars:long currency:string amount:long = InputStorePaymentPurpose;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | The user to which the stars should be gifted. |
| stars | long | Amount of stars to gift |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Type
InputStorePaymentPurpose

## Related pages
