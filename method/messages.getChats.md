# messages.getChats
Returns chat basic info on their IDs.

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;
---functions---
messages.getChats#49e9528f id:Vector<long> = messages.Chats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | Vector<long> | List of chat IDs |


## Result
messages.Chats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

