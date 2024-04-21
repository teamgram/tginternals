# phone.editGroupCallParticipant
Edit information about a given group call participant

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
phone.editGroupCallParticipant#a5273abf flags:# call:InputGroupCall participant:InputPeer muted:flags.0?Bool volume:flags.1?int raise_hand:flags.2?Bool video_stopped:flags.3?Bool video_paused:flags.4?Bool presentation_paused:flags.5?Bool = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| call | InputGroupCall | The group call |
| participant | InputPeer | The group call participant (can also be the user itself) |
| muted | flags.0?Bool | Whether to mute or unmute the specified participant |
| volume | flags.1?int | New volume |
| raise_hand | flags.2?Bool | Raise or lower hand |
| video_stopped | flags.3?Bool | Start or stop the video stream |
| video_paused | flags.4?Bool | Pause or resume the video stream |
| presentation_paused | flags.5?Bool | Pause or resume the screen sharing stream |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | GROUPCALL_FORBIDDEN | The group call has already ended. |
| 400 | PARTICIPANT_JOIN_MISSING | Trying to enable a presentation, when the user hasn't joined the Video Chat with phone.joinGroupCall. |
| 400 | USER_VOLUME_INVALID | The specified user volume is invalid. |

