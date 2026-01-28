# payments.uniqueStarGiftValueInfo
Information about the value of a collectible gift ».

```
payments.uniqueStarGiftValueInfo#512fe446 flags:# last_sale_on_fragment:flags.1?true value_is_average:flags.6?true currency:string value:long initial_sale_date:int initial_sale_stars:long initial_sale_price:long last_sale_date:flags.0?int last_sale_price:flags.0?long floor_price:flags.2?long average_price:flags.3?long listed_count:flags.4?int fragment_listed_count:flags.5?int fragment_listed_url:flags.5?string = payments.UniqueStarGiftValueInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| last_sale_on_fragment | flags.1?true | If set, the last sale was completed on Fragment. |
| value_is_average | flags.6?true | If set, the value is calculated from the average value of sold gifts of the same type. Otherwise, it is based on the sale price of the gift. |
| currency | string | Three-letter ISO 4217 currency code (a localized fiat currency used to represent prices and price estimations in this constructor). |
| value | long | Estimated value of the gift, in the smallest unit of the currency specified in currency. |
| initial_sale_date | int | Initial purchase date of the gift. |
| initial_sale_stars | long | Initial purchase price in Stars. |
| initial_sale_price | long | Initial purchase price in the smallest unit of the currency specified in currency (automatically converted from initial_sale_stars). |
| last_sale_date | flags.0?int | Last resale date of the gift. |
| last_sale_price | flags.0?long | Last resale price, in the smallest unit of the currency specified in currency. |
| floor_price | flags.2?long | The current minimum price of collectible gifts of the same type, in the smallest unit of the currency specified in currency. |
| average_price | flags.3?long | The current average sale price of collectible gifts of the same type, in the smallest unit of the currency specified in currency. |
| listed_count | flags.4?int | Number of gifts of the same type currently being resold on Telegram. |
| fragment_listed_count | flags.5?int | Number of gifts of the same type currently being resold on fragment. |
| fragment_listed_url | flags.5?string | Fragment link to the listing of gifts of the same type currently being resold on fragment. |


## Type
payments.UniqueStarGiftValueInfo

## Related pages
