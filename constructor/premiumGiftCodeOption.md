# premiumGiftCodeOption
Contains info about a giveaway/gift option.

```
premiumGiftCodeOption#257e962b flags:# users:int months:int store_product:flags.0?string store_quantity:flags.1?int currency:string amount:long = PremiumGiftCodeOption;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| users | int | Number of users which will be able to activate the gift codes. |
| months | int | Duration in months of each gifted Telegram Premium subscription. |
| store_product | flags.0?string | Identifier of the store product associated with the option, official apps only. |
| store_quantity | flags.1?int | Number of times the store product must be paid |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Type
PremiumGiftCodeOption

## Related pages
