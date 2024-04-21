# messages.editChatAdmin
Make a user admin in a basic group.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.editChatAdmin#a85bd1c2 chat_id:long user_id:InputUser is_admin:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chat_id | long | The ID of the group |
| user_id | InputUser | The user to make admin |
| is_admin | Bool | Whether to make them admin |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 400 | USER_NOT_PARTICIPANT | You're not a member of this supergroup/channel. |

