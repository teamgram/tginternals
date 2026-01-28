# messages.getOutboxReadDate
Get the exact read date of one of our messages, sent to a private chat with another user.

```
outboxReadDate#3bb842ac date:int = OutboxReadDate;
---functions---
messages.getOutboxReadDate#8c4bfe5d peer:InputPeer msg_id:int = OutboxReadDate;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The user to whom we sent the message. |
| msg_id | int | The message ID. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MESSAGE_NOT_READ_YET | The specified message wasn't read yet. |
| 400 | MESSAGE_TOO_OLD | The message is too old, the requested information is not available. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 403 | USER_PRIVACY_RESTRICTED | The user's privacy settings do not allow you to do this. |
| 403 | YOUR_PRIVACY_RESTRICTED | You cannot fetch the read date of this message because you have disallowed other users to do so for your messages; to fix, allow other users to see your exact last online date OR purchase a Telegram Premium subscription. |

