# payments.getResaleStarGifts
Get collectible gifts of a specific type currently on resale, see here » for more info.

```
payments.resaleStarGifts#947a12df flags:# count:int gifts:Vector<StarGift> next_offset:flags.0?string attributes:flags.1?Vector<StarGiftAttribute> attributes_hash:flags.1?long chats:Vector<Chat> counters:flags.2?Vector<StarGiftAttributeCounter> users:Vector<User> = payments.ResaleStarGifts;
---functions---
payments.getResaleStarGifts#7a5fa236 flags:# sort_by_price:flags.1?true sort_by_num:flags.2?true attributes_hash:flags.0?long gift_id:long attributes:flags.3?Vector<StarGiftAttributeId> offset:string limit:int = payments.ResaleStarGifts;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| sort_by_price | flags.1?true | Sort gifts by price (ascending). |
| sort_by_num | flags.2?true | Sort gifts by number (ascending). |
| attributes_hash | flags.0?long | If a previous call to the method was made and payments.resaleStarGifts.attributes_hash was set, pass it here to avoid returning any results if they haven't changed. Otherwise, set this flag and pass 0 to return payments.resaleStarGifts.attributes_hash and payments.resaleStarGifts.attributes, these two fields will not be set if this flag is not set. |
| gift_id | long | Mandatory identifier of the base gift from which the collectible gift was upgraded. |
| attributes | flags.3?Vector<StarGiftAttributeId> | Optionally filter gifts with the specified attributes. If no attributes of a specific type are specified, all attributes of that type are allowed. |
| offset | string | Offset for pagination. If not equal to an empty string, payments.resaleStarGifts.counters will not be set to avoid returning the counters every time a new page is fetched. |
| limit | int | Maximum number of results to return, see pagination |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STARGIFT_INVALID | The passed gift is invalid. |

