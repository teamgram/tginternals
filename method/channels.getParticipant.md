# channels.getParticipant
Get info about a channel/supergroup participant

```
channels.channelParticipant#dfb80317 participant:ChannelParticipant chats:Vector<Chat> users:Vector<User> = channels.ChannelParticipant;
---functions---
channels.getParticipant#a0ab6cc6 channel:InputChannel participant:InputPeer = channels.ChannelParticipant;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Channel/supergroup |
| participant | InputPeer | Participant to get info about |


## Result
channels.ChannelParticipant

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PARTICIPANT_ID_INVALID | The specified participant ID is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 400 | USER_NOT_PARTICIPANT | You're not a member of this supergroup/channel. |

