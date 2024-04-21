# messages.sendEncryptedService
Sends a service message to a secret chat.

```
messages.sentEncryptedMessage#560f8935 date:int = messages.SentEncryptedMessage;
messages.sentEncryptedFile#9493ff32 date:int file:EncryptedFile = messages.SentEncryptedMessage;
---functions---
messages.sendEncryptedService#32d439a4 peer:InputEncryptedChat random_id:long data:bytes = messages.SentEncryptedMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputEncryptedChat | Secret chat ID |
| random_id | long | Unique client message ID required to prevent message resending |
| data | bytes | TL-serialization of  DecryptedMessage type, encrypted with a key generated during chat initialization |


## Result
messages.SentEncryptedMessage

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | DATA_INVALID | Encrypted data invalid. |
| 400 | ENCRYPTION_DECLINED | The secret chat was declined. |
| 400 | ENCRYPTION_ID_INVALID | The provided secret chat ID is invalid. |
| 500 | MSG_WAIT_FAILED | A waiting call returned an error. |
| 403 | USER_DELETED | You can't send this secret message because the other participant deleted their account. |
| 403 | USER_IS_BLOCKED | You were blocked by this user. |

