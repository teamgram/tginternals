# messageActionStarGift
You received a gift, see here » for more info.

```
messageActionStarGift#f24de7fa flags:# name_hidden:flags.0?true saved:flags.2?true converted:flags.3?true upgraded:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true prepaid_upgrade:flags.13?true upgrade_separate:flags.16?true gift:StarGift message:flags.1?TextWithEntities convert_stars:flags.4?long upgrade_msg_id:flags.5?int upgrade_stars:flags.8?long from_id:flags.11?Peer peer:flags.12?Peer saved_id:flags.12?long prepaid_upgrade_hash:flags.14?string gift_msg_id:flags.15?int = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| name_hidden | flags.0?true | If set, the name of the sender of the gift will be hidden if the destination user decides to display the gift on their profile |
| saved | flags.2?true | Whether this gift was added to the destination user's profile (may be toggled using payments.saveStarGift and fetched using payments.getSavedStarGifts) |
| converted | flags.3?true | Whether this gift was converted to Telegram Stars and cannot be displayed on the profile anymore. |
| upgraded | flags.5?true | This gift was upgraded to a collectible gift ». |
| refunded | flags.9?true | This gift is not available anymore because a request to refund the payment related to this gift was made, and the money was returned. |
| can_upgrade | flags.10?true | If set, this gift can be upgraded to a collectible gift; can only be set for the receiver of a gift. |
| prepaid_upgrade | flags.13?true | The sender has already pre-paid for the upgrade of this gift to a collectible gift. |
| upgrade_separate | flags.16?true | This service message is the notification of a separate pre-payment for the upgrade of a gift we own. |
| gift | StarGift | Info about the gift |
| message | flags.1?TextWithEntities | Additional message from the sender of the gift |
| convert_stars | flags.4?long | The receiver of this gift may convert it to this many Telegram Stars, instead of displaying it on their profile page.convert_stars will be equal to stars only if the gift was bought using recently bought Telegram Stars, otherwise it will be less than stars. |
| upgrade_msg_id | flags.5?int | If set, this gift was upgraded to a collectible gift, and the corresponding messageActionStarGiftUnique is available at the specified message ID. |
| upgrade_stars | flags.8?long | The number of Telegram Stars the user can pay to convert the gift into a collectible gift ». |
| from_id | flags.11?Peer | Sender of the gift (unset for anonymous gifts). |
| peer | flags.12?Peer | Receiver of the gift. |
| saved_id | flags.12?long | For channel gifts, ID to use in inputSavedStarGiftChat constructors. |
| prepaid_upgrade_hash | flags.14?string | Hash to prepay for a gift upgrade separately ». |
| gift_msg_id | flags.15?int | For separate upgrades, the identifier of the message with the gift whose upgrade was prepaid (only valid for the receiver of the service message). |


## Type
MessageAction

## Related pages
