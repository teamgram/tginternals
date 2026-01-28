# messages.setChatAvailableReactions
Change the set of message reactions » that can be used in a certain group, supergroup or channel

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.setChatAvailableReactions#864b2581 flags:# peer:InputPeer available_reactions:ChatReactions reactions_limit:flags.0?int paid_enabled:flags.1?Bool = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Group where to apply changes |
| available_reactions | ChatReactions | Allowed reaction emojis |
| reactions_limit | flags.0?int | This flag may be used to impose a custom limit of unique reactions (i.e. a customizable version of appConfig.reactions_uniq_max); this field and the other info set by the method will then be available to users in channelFull and chatFull. If this flag is not set, the previously configured reactions_limit will not be altered. |
| paid_enabled | flags.1?Bool | If this flag is set and a Bool is passed, the method will enable or disable paid message reactions ». If this flag is not set, the previously stored setting will not be changed. |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_NOT_MODIFIED | No changes were made to chat information because the new information you passed is identical to the current information. |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | REACTION_INVALID | The specified reaction is invalid. |

