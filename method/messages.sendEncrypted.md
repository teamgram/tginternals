# messages.sendEncrypted
Sends a text message to a secret chat.

```
messages.sentEncryptedMessage#560f8935 date:int = messages.SentEncryptedMessage;
messages.sentEncryptedFile#9493ff32 date:int file:EncryptedFile = messages.SentEncryptedMessage;
---functions---
messages.sendEncrypted#44fa7a15 flags:# silent:flags.0?true peer:InputEncryptedChat random_id:long data:bytes = messages.SentEncryptedMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| silent | flags.0?true | Send encrypted message without a notification |
| peer | InputEncryptedChat | Secret chat ID |
| random_id | long | Unique client message ID, necessary to avoid message resending |
| data | bytes | TL-serialization of DecryptedMessage type, encrypted with a key that was created during chat initialization |


## Result
messages.SentEncryptedMessage

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | DATA_INVALID | Encrypted data invalid. |
| 400 | DATA_TOO_LONG | Data too long. |
| 400 | ENCRYPTION_DECLINED | The secret chat was declined. |
| 500 | MSG_WAIT_FAILED | A waiting call returned an error. |
| 403 | USER_IS_BLOCKED | You were blocked by this user. |

