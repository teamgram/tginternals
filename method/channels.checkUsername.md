# channels.checkUsername
Check if a username is free and can be assigned to a channel/supergroup

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.checkUsername#10e6bd2c channel:InputChannel username:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | The channel/supergroup that will assigned the specified username |
| username | string | The username to check |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNELS_ADMIN_PUBLIC_TOO_MUCH | You're admin of too many public channels, make some channels private to change the username of this channel. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USERNAME_INVALID | The provided username is not valid. |
| 400 | USERNAME_OCCUPIED | The provided username is already occupied. |
| 400 | USERNAME_PURCHASE_AVAILABLE | The specified username can be purchased on https://fragment.com. |

