# users.getFullUser
Returns extended user info by ID.

```
users.userFull#3b6d152e full_user:UserFull chats:Vector<Chat> users:Vector<User> = users.UserFull;
---functions---
users.getFullUser#b60f5918 id:InputUser = users.UserFull;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | InputUser | User ID |


## Result
users.UserFull

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USERNAME_OCCUPIED | The provided username is already occupied. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

