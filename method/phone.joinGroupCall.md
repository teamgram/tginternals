# phone.joinGroupCall
Join a group call

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
phone.joinGroupCall#b132ff7b flags:# muted:flags.0?true video_stopped:flags.2?true call:InputGroupCall join_as:InputPeer invite_hash:flags.1?string params:DataJSON = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| muted | flags.0?true | If set, the user will be muted by default upon joining. |
| video_stopped | flags.2?true | If set, the user's video will be disabled by default upon joining. |
| call | InputGroupCall | The group call |
| join_as | InputPeer | Join the group call, presenting yourself as the specified user/channel |
| invite_hash | flags.1?string | The invitation hash from the invite link », if provided allows speaking in a livestream or muted group chat. |
| params | DataJSON | WebRTC parameters |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DATA_JSON_INVALID | The provided JSON data is invalid. |
| 403 | GROUPCALL_FORBIDDEN | The group call has already ended. |
| 400 | GROUPCALL_INVALID | The specified group call is invalid. |
| 400 | GROUPCALL_SSRC_DUPLICATE_MUCH | The app needs to retry joining the group call with a new SSRC value. |
| 400 | JOIN_AS_PEER_INVALID | The specified peer cannot be used to join a group call. |

