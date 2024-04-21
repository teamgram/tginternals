# users.getUsers
Returns basic user info according to their identifiers.

```
---functions---
users.getUsers#d91a548 id:Vector<InputUser> = Vector<User>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | Vector<InputUser> | List of user identifiers |


## Result
Vector<User>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | FROM_MESSAGE_BOT_DISABLED | Bots can't use fromMessage min constructors. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |

