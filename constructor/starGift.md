# starGift
Represents a star gift, see here » for more info.

```
starGift#80ac53c3 flags:# limited:flags.0?true sold_out:flags.1?true birthday:flags.2?true require_premium:flags.7?true limited_per_user:flags.8?true id:long sticker:Document stars:long availability_remains:flags.0?int availability_total:flags.0?int availability_resale:flags.4?long convert_stars:long first_sale_date:flags.1?int last_sale_date:flags.1?int upgrade_stars:flags.3?long resell_min_stars:flags.4?long title:flags.5?string released_by:flags.6?Peer per_user_total:flags.8?int per_user_remains:flags.8?int locked_until_date:flags.9?int = StarGift;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| limited | flags.0?true | Whether this is a limited-supply gift. |
| sold_out | flags.1?true | Whether this gift sold out and cannot be bought anymore. |
| birthday | flags.2?true | Whether this is a birthday-themed gift |
| require_premium | flags.7?true | This gift can only be bought by users with a Premium subscription. |
| limited_per_user | flags.8?true | If set, the maximum number of gifts of this type that can be owned by a single user is limited and specified in per_user_total, and the remaining slots for the current user in per_user_remains. |
| id | long | Identifier of the gift |
| sticker | Document | Sticker that represents the gift. |
| stars | long | Price of the gift in Telegram Stars. |
| availability_remains | flags.0?int | For limited-supply gifts: the remaining number of gifts that may be bought. |
| availability_total | flags.0?int | For limited-supply gifts: the total number of gifts that was available in the initial supply. |
| availability_resale | flags.4?long | The total number of (upgraded to collectibles) gifts of this type currently on resale |
| convert_stars | long | The receiver of this gift may convert it to this many Telegram Stars, instead of displaying it on their profile page.convert_stars will be equal to stars only if the gift was bought using recently bought Telegram Stars, otherwise it will be less than stars. |
| first_sale_date | flags.1?int | For sold out gifts only: when was the gift first bought. |
| last_sale_date | flags.1?int | For sold out gifts only: when was the gift last bought. |
| upgrade_stars | flags.3?long | The number of Telegram Stars the user can pay to convert the gift into a collectible gift ». |
| resell_min_stars | flags.4?long | The minimum price in Stars for gifts of this type currently on resale. |
| title | flags.5?string | Title of the gift |
| released_by | flags.6?Peer | This gift was released by the specified peer. |
| per_user_total | flags.8?int | Maximum number of gifts of this type that can be owned by any user. |
| per_user_remains | flags.8?int | Remaining number of gifts of this type that can be owned by the current user. |
| locked_until_date | flags.9?int | If set, the specified gift possibly cannot be sent until the specified date, see here » for the full flow. |


## Type
StarGift

## Related pages
