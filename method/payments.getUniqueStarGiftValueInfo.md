# payments.getUniqueStarGiftValueInfo
Get information about the value of a collectible gift ».

```
payments.uniqueStarGiftValueInfo#512fe446 flags:# last_sale_on_fragment:flags.1?true value_is_average:flags.6?true currency:string value:long initial_sale_date:int initial_sale_stars:long initial_sale_price:long last_sale_date:flags.0?int last_sale_price:flags.0?long floor_price:flags.2?long average_price:flags.3?long listed_count:flags.4?int fragment_listed_count:flags.5?int fragment_listed_url:flags.5?string = payments.UniqueStarGiftValueInfo;
---functions---
payments.getUniqueStarGiftValueInfo#4365af6b slug:string = payments.UniqueStarGiftValueInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| slug | string | slug from a starGiftUnique. |


## Result
payments.UniqueStarGiftValueInfo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STARGIFT_SLUG_INVALID | The specified gift slug is invalid. |

