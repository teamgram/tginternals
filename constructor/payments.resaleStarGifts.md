# payments.resaleStarGifts
List of gifts currently on resale ».

```
payments.resaleStarGifts#947a12df flags:# count:int gifts:Vector<StarGift> next_offset:flags.0?string attributes:flags.1?Vector<StarGiftAttribute> attributes_hash:flags.1?long chats:Vector<Chat> counters:flags.2?Vector<StarGiftAttributeCounter> users:Vector<User> = payments.ResaleStarGifts;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of results. |
| gifts | Vector<StarGift> | Collectible gifts on resale (may be less than count, in which case next_offset will be set). |
| next_offset | flags.0?string | Offset for pagination, pass this to payments.getResaleStarGifts.offset to fetch the next results. |
| attributes | flags.1?Vector<StarGiftAttribute> | Possible gift attributes, only set if payments.getResaleStarGifts.attributes_hash is set (on the first call, it must be equal to 0). |
| attributes_hash | flags.1?long | Hash of the attributes field, pass this to payments.getResaleStarGifts.attributes_hash to avoid returning any attributes (flag not set) if they haven't changed. |
| chats | Vector<Chat> | Chats mentioned in the attributes. |
| counters | flags.2?Vector<StarGiftAttributeCounter> | Indicates the total number of gifts that have a specific attribute, only set if payments.getResaleStarGifts.offset is empty (since this field is not related to the current result page but to all of them, it's only returned on the first page). |
| users | Vector<User> | Users mentioned in the attributes. |


## Type
payments.ResaleStarGifts

## Related pages
