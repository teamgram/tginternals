# channels.getChannels
Get info about channels/supergroups

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;
---functions---
channels.getChannels#a7f6bbb id:Vector<InputChannel> = messages.Chats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | Vector<InputChannel> | IDs of channels/supergroups to get info about |


## Result
messages.Chats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |

