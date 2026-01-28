# StarGift
Represents a star gift, see here » for more info.

```
starGift#80ac53c3 flags:# limited:flags.0?true sold_out:flags.1?true birthday:flags.2?true require_premium:flags.7?true limited_per_user:flags.8?true id:long sticker:Document stars:long availability_remains:flags.0?int availability_total:flags.0?int availability_resale:flags.4?long convert_stars:long first_sale_date:flags.1?int last_sale_date:flags.1?int upgrade_stars:flags.3?long resell_min_stars:flags.4?long title:flags.5?string released_by:flags.6?Peer per_user_total:flags.8?int per_user_remains:flags.8?int locked_until_date:flags.9?int = StarGift;
starGiftUnique#1befe865 flags:# require_premium:flags.6?true resale_ton_only:flags.7?true theme_available:flags.9?true id:long gift_id:long title:string slug:string num:int owner_id:flags.0?Peer owner_name:flags.1?string owner_address:flags.2?string attributes:Vector<StarGiftAttribute> availability_issued:int availability_total:int gift_address:flags.3?string resell_amount:flags.4?Vector<StarsAmount> released_by:flags.5?Peer value_amount:flags.8?long value_currency:flags.8?string theme_peer:flags.10?Peer = StarGift;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| starGift | Represents a star gift, see here » for more info. |
| starGiftUnique | Represents a collectible star gift, see here » for more info.The sticker that represents the gift is contained in a starGiftAttributeModel object in attributes. |


## Methods
| Method | Description |
| ---- | ----------- |


