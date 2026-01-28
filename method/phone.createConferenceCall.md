# phone.createConferenceCall
Create and optionally join a new conference call.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
phone.createConferenceCall#7d0444bb flags:# muted:flags.0?true video_stopped:flags.2?true join:flags.3?true random_id:int public_key:flags.3?int256 block:flags.3?bytes params:flags.3?DataJSON = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| muted | flags.0?true | If set, mute our microphone when joining the call (can only be used if join is set). |
| video_stopped | flags.2?true | If set, our video stream is disabled (can only be used if join is set). |
| join | flags.3?true | If set, also join the call, otherwise just create the call link. |
| random_id | int | Unique client message ID required to prevent creation of duplicate group calls. |
| public_key | flags.3?int256 | Public key (can only be used if join is set). |
| block | flags.3?bytes | Initial blockchain block (can only be used if join is set). |
| params | flags.3?DataJSON | Parameters from tgcalls (can only be used if join is set). |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

