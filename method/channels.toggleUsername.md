# channels.toggleUsername
Activate or deactivate a purchased fragment.com username associated to a supergroup or channel we own.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.toggleUsername#50f24105 channel:InputChannel username:string active:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Supergroup or channel |
| username | string | Username |
| active | Bool | Whether to activate or deactivate the username |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | USERNAMES_ACTIVE_TOO_MUCH | The maximum number of active usernames was reached. |
| 400 | USERNAME_INVALID | The provided username is not valid. |

