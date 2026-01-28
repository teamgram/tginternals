# fragment.collectibleInfo
Info about a fragment collectible.

```
fragment.collectibleInfo#6ebdff91 purchase_date:int currency:string amount:long crypto_currency:string crypto_amount:long url:string = fragment.CollectibleInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| purchase_date | int | Purchase date (unixtime) |
| currency | string | Three-letter ISO 4217 currency code for amount |
| amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| crypto_currency | string | Cryptocurrency name. |
| crypto_amount | long | Price, in the smallest units of the cryptocurrency. |
| url | string | Fragment URL with more info about the collectible |


## Type
fragment.CollectibleInfo

## Related pages
