# payments.upgradeStarGift
Upgrade a gift to a collectible gift: can only be used if the upgrade was already paid by the gift sender; see here » for more info on the full flow (including the different flow to use in case the upgrade was not paid by the gift sender).

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
payments.upgradeStarGift#aed6e4f5 flags:# keep_original_details:flags.0?true stargift:InputSavedStarGift = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| keep_original_details | flags.0?true | Set this flag to keep the original gift text, sender and receiver in the upgraded gift as a starGiftAttributeOriginalDetails attribute. |
| stargift | InputSavedStarGift | The gift to upgrade |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PAYMENT_REQUIRED | Payment is required for this action, see here » for more info. |
| 400 | SAVED_ID_EMPTY | The passed inputSavedStarGiftChat.saved_id is empty. |
| 400 | STARGIFT_ALREADY_CONVERTED | The specified star gift was already converted to Stars. |
| 400 | STARGIFT_ALREADY_UPGRADED | The specified gift was already upgraded to a collectible gift. |
| 400 | STARGIFT_UPGRADE_UNAVAILABLE | A received gift can only be upgraded to a collectible gift if the messageActionStarGift/savedStarGift.can_upgrade flag is set. |

