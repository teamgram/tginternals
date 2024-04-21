# channels.deleteParticipantHistory
Delete all messages sent by a specific participant of a given supergroup

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
---functions---
channels.deleteParticipantHistory#367544db channel:InputChannel participant:InputPeer = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Supergroup |
| participant | InputPeer | The participant whose messages should be deleted |


## Result
messages.AffectedHistory

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PARTICIPANT_ID_INVALID | The specified participant ID is invalid. |

