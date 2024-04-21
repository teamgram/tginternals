# messages.getFullChat
Get full info about a basic group.

```
messages.chatFull#e5d7d19c full_chat:ChatFull chats:Vector<Chat> users:Vector<User> = messages.ChatFull;
---functions---
messages.getFullChat#aeb00b34 chat_id:long = messages.ChatFull;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chat_id | long | Basic group ID. |


## Result
messages.ChatFull

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

