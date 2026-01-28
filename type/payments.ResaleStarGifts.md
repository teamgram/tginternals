# payments.ResaleStarGifts
List of gifts currently on resale ».

```
payments.resaleStarGifts#947a12df flags:# count:int gifts:Vector<StarGift> next_offset:flags.0?string attributes:flags.1?Vector<StarGiftAttribute> attributes_hash:flags.1?long chats:Vector<Chat> counters:flags.2?Vector<StarGiftAttributeCounter> users:Vector<User> = payments.ResaleStarGifts;

---functions---

payments.getResaleStarGifts#7a5fa236 flags:# sort_by_price:flags.1?true sort_by_num:flags.2?true attributes_hash:flags.0?long gift_id:long attributes:flags.3?Vector<StarGiftAttributeId> offset:string limit:int = payments.ResaleStarGifts;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.resaleStarGifts | List of gifts currently on resale ». |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getResaleStarGifts | Get collectible gifts of a specific type currently on resale, see here » for more info.sort_by_price and sort_by_num are mutually exclusive, if neither are set results are sorted by the unixtime (descending) when their resell price was last changed. |


