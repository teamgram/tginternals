# starsTopupOption
Telegram Stars topup option.

```
starsTopupOption#bd915c0 flags:# extended:flags.1?true stars:long store_product:flags.0?string currency:string amount:long = StarsTopupOption;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| extended | flags.1?true | If set, the option must only be shown in the full list of topup options. |
| stars | long | Amount of Telegram stars. |
| store_product | flags.0?string | Identifier of the store product associated with the option, official apps only. |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Price of the product in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Type
StarsTopupOption

## Related pages
