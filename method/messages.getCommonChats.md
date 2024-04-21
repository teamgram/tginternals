# messages.getCommonChats
Get chats in common with a user

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;
---functions---
messages.getCommonChats#e40ca104 user_id:InputUser max_id:long limit:int = messages.Chats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | User ID |
| max_id | long | Maximum ID of chat to return (see pagination) |
| limit | int | Maximum number of results to return, see pagination |


## Result
messages.Chats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

