# payments.transferStarGift
Transfer a collectible gift to another user or channel: can only be used if transfer is free (i.e. messageActionStarGiftUnique.transfer_stars is not set); see here » for more info on the full flow (including the different flow to use in case the transfer isn't free).

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
payments.transferStarGift#7f18176a stargift:InputSavedStarGift to_id:InputPeer = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stargift | InputSavedStarGift | The gift to transfer. |
| to_id | InputPeer | Destination peer. |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PAYMENT_REQUIRED | Payment is required for this action, see here » for more info. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | SAVED_ID_EMPTY | The passed inputSavedStarGiftChat.saved_id is empty. |
| 400 | STARGIFT_NOT_FOUND | The specified gift was not found. |
| 400 | STARGIFT_OWNER_INVALID | You cannot transfer or sell a gift owned by another user. |
| 400 | STARGIFT_PEER_INVALID | The specified inputSavedStarGiftChat.peer is invalid. |

