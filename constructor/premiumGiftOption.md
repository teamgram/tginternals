# premiumGiftOption
Telegram Premium gift option

```
premiumGiftOption#74c34319 flags:# months:int currency:string amount:long bot_url:string store_product:flags.0?string = PremiumGiftOption;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| months | int | Duration of gifted Telegram Premium subscription |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Price of the product in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| bot_url | string | An invoice deep link » to an invoice for in-app payment, using the official Premium bot; may be empty if direct payment isn't available. |
| store_product | flags.0?string | An identifier for the App Store/Play Store product associated with the Premium gift. |


## Type
PremiumGiftOption

## Related pages
