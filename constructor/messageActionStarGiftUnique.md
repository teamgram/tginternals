# messageActionStarGiftUnique
A gift » was upgraded to a collectible gift ».

```
messageActionStarGiftUnique#34f762f3 flags:# upgrade:flags.0?true transferred:flags.1?true saved:flags.2?true refunded:flags.5?true prepaid_upgrade:flags.11?true gift:StarGift can_export_at:flags.3?int transfer_stars:flags.4?long from_id:flags.6?Peer peer:flags.7?Peer saved_id:flags.7?long resale_amount:flags.8?StarsAmount can_transfer_at:flags.9?int can_resell_at:flags.10?int = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| upgrade | flags.0?true | If set, this collectible was upgraded » to a collectible gift from a previously received or sent (depending on the out flag of the containing messageService) non-collectible gift. |
| transferred | flags.1?true | If set, this collectible was transferred (either to the current user or by the current user to the other user in the private chat, depending on the out flag of the containing messageService). |
| saved | flags.2?true | If set, this gift is visible on the user or channel's profile page; can only be set for the receiver of a gift. |
| refunded | flags.5?true | This gift was upgraded to a collectible gift » and then re-downgraded to a regular gift because a request to refund the payment related to the upgrade was made, and the money was returned. |
| prepaid_upgrade | flags.11?true | The sender has pre-paid for the upgrade of this gift to a collectible gift. |
| gift | StarGift | The collectible gift. |
| can_export_at | flags.3?int | If set, indicates that the current gift can't be exported to the TON blockchain » yet: the owner will be able to export it at the specified unixtime. |
| transfer_stars | flags.4?long | If set, indicates that the gift can be transferred » to another user by paying the specified amount of stars. |
| from_id | flags.6?Peer | Sender of the gift (unset for anonymous gifts). |
| peer | flags.7?Peer | Receiver of the gift. |
| saved_id | flags.7?long | For channel gifts, ID to use in inputSavedStarGiftChat constructors. |
| resale_amount | flags.8?StarsAmount | Resale price of the gift. |
| can_transfer_at | flags.9?int | If set, indicates that the current gift can't be transferred » yet: the owner will be able to transfer it at the specified unixtime. |
| can_resell_at | flags.10?int | If set, indicates that the current gift can't be resold » yet: the owner will be able to put it up for sale at the specified unixtime. |


## Type
MessageAction

## Related pages
