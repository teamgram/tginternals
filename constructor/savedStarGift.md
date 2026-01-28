# savedStarGift
Represents a gift owned by a peer.

```
savedStarGift#19a9b572 flags:# name_hidden:flags.0?true unsaved:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true pinned_to_top:flags.12?true upgrade_separate:flags.17?true from_id:flags.1?Peer date:int gift:StarGift message:flags.2?TextWithEntities msg_id:flags.3?int saved_id:flags.11?long convert_stars:flags.4?long upgrade_stars:flags.6?long can_export_at:flags.7?int transfer_stars:flags.8?long can_transfer_at:flags.13?int can_resell_at:flags.14?int collection_id:flags.15?Vector<int> prepaid_upgrade_hash:flags.16?string = SavedStarGift;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| name_hidden | flags.0?true | If set, the gift sender in from_id and the message are set only for the receiver of the gift. |
| unsaved | flags.5?true | If set, the gift is not pinned on the user's profile. |
| refunded | flags.9?true | This gift was upgraded to a collectible gift » and then re-downgraded to a regular gift because a request to refund the payment related to the upgrade was made, and the money was returned. |
| can_upgrade | flags.10?true | Only set for non-collectible gifts, if they can be upgraded to a collectible gift ». |
| pinned_to_top | flags.12?true | Whether this gift is pinned on top of the user's profile page. |
| upgrade_separate | flags.17?true | If set, someone already separately pre-paid for the upgrade of this gift. |
| from_id | flags.1?Peer | Sender of the gift (unset for anonymous gifts). |
| date | int | Reception date of the gift. |
| gift | StarGift | The collectible gift. |
| message | flags.2?TextWithEntities | Message attached to the gift. |
| msg_id | flags.3?int | For gifts received by users, ID to use in inputSavedStarGiftUser constructors. |
| saved_id | flags.11?long | For gifts received by channels, ID to use in inputSavedStarGiftChat constructors. |
| convert_stars | flags.4?long | For non-collectible gifts, the receiver of this gift may convert it to this many Telegram Stars, instead of displaying it on their profile page. |
| upgrade_stars | flags.6?long | Only for pre-paid non-collectible gifts, the number of Telegram Stars the sender has already paid to convert the gift into a collectible gift » (this is different from the meaning of the flag in messageActionStarGift, where it signals the upgrade price for not yet upgraded gifts). |
| can_export_at | flags.7?int | If set, indicates that the current gift can't be exported to the TON blockchain » yet: the owner will be able to export it at the specified unixtime. |
| transfer_stars | flags.8?long | If set, indicates that the gift can be transferred » to another user by paying the specified amount of stars. |
| can_transfer_at | flags.13?int | If set, indicates that the current gift can't be transferred » yet: the owner will be able to transfer it at the specified unixtime. |
| can_resell_at | flags.14?int | If set, indicates that the current gift can't be resold » yet: the owner will be able to put it up for sale at the specified unixtime. |
| collection_id | flags.15?Vector<int> | IDs of the collections » that this gift is a part of. |
| prepaid_upgrade_hash | flags.16?string | Hash to prepay for a gift upgrade separately ». |


## Type
SavedStarGift

## Related pages
