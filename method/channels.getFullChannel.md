# channels.getFullChannel
Get full info about a supergroup, gigagroup or channel

```
messages.chatFull#e5d7d19c full_chat:ChatFull chats:Vector<Chat> users:Vector<User> = messages.ChatFull;
---functions---
channels.getFullChannel#8736a09 channel:InputChannel = messages.ChatFull;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | The channel, supergroup or gigagroup to get info about |


## Result
messages.ChatFull

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHANNEL_PUBLIC_GROUP_NA | channel/supergroup not available. |
| 400 | CHAT_NOT_MODIFIED | No changes were made to chat information because the new information you passed is identical to the current information. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |

