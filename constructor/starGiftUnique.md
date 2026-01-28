# starGiftUnique
Represents a collectible star gift, see here » for more info.

```
starGiftUnique#1befe865 flags:# require_premium:flags.6?true resale_ton_only:flags.7?true theme_available:flags.9?true id:long gift_id:long title:string slug:string num:int owner_id:flags.0?Peer owner_name:flags.1?string owner_address:flags.2?string attributes:Vector<StarGiftAttribute> availability_issued:int availability_total:int gift_address:flags.3?string resell_amount:flags.4?Vector<StarsAmount> released_by:flags.5?Peer value_amount:flags.8?long value_currency:flags.8?string theme_peer:flags.10?Peer = StarGift;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| require_premium | flags.6?true | This gift can only be bought by users with a Premium subscription. |
| resale_ton_only | flags.7?true | Whether the gift can be bought only using Toncoins. |
| theme_available | flags.9?true | A chat theme associated to this gift is available, see here » for more info on how to use it. |
| id | long | Identifier of the collectible gift. |
| gift_id | long | Unique ID of the gift. |
| title | string | Collectible title. |
| slug | string | Slug that can be used to create a collectible gift deep link », or elsewhere in the API where a collectible slug is accepted. |
| num | int | Unique identifier of this collectible gift among all (already upgraded) collectible gifts of the same type. |
| owner_id | flags.0?Peer | The owner of the gift. |
| owner_name | flags.1?string | The name of the owner if neither owner_id nor owner_address are set. |
| owner_address | flags.2?string | For NFTs on the TON blockchain, contains the address of the owner (append it to the ton_blockchain_explorer_url client configuration value » to obtain a link with information about the address). |
| attributes | Vector<StarGiftAttribute> | Collectible attributes |
| availability_issued | int | Total number of gifts of the same type that were upgraded to a collectible gift. |
| availability_total | int | Total number of gifts of the same type that can be upgraded or were already upgraded to a collectible gift. |
| gift_address | flags.3?string | For NFTs on the TON blockchain, contains the address of the NFT (append it to the ton_blockchain_explorer_url client configuration value » to obtain a link with information about the address). |
| resell_amount | flags.4?Vector<StarsAmount> | Resale price of the gift. |
| released_by | flags.5?Peer | This gift was released by the specified peer. |
| value_amount | flags.8?long | Price of the gift. |
| value_currency | flags.8?string | Currency for the gift's price. |
| theme_peer | flags.10?Peer | The current chat where the associated chat theme is installed, if any (gift-based themes can only be installed in one chat at a time). |


## Type


## Related pages
