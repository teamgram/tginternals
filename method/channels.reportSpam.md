# channels.reportSpam
Reports some messages from a user in a supergroup as spam; requires administrator rights in the supergroup

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.reportSpam#f44a8315 channel:InputChannel participant:InputPeer id:Vector<int> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Supergroup |
| participant | InputPeer | Participant whose messages should be reported |
| id | Vector<int> | IDs of spam messages |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

