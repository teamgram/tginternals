# messages.sendEncryptedFile
Sends a message with a file attachment to a secret chat

```
messages.sentEncryptedMessage#560f8935 date:int = messages.SentEncryptedMessage;
messages.sentEncryptedFile#9493ff32 date:int file:EncryptedFile = messages.SentEncryptedMessage;
---functions---
messages.sendEncryptedFile#5559481d flags:# silent:flags.0?true peer:InputEncryptedChat random_id:long data:bytes file:InputEncryptedFile = messages.SentEncryptedMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| silent | flags.0?true | Whether to send the file without triggering a notification |
| peer | InputEncryptedChat | Secret chat ID |
| random_id | long | Unique client message ID necessary to prevent message resending |
| data | bytes | TL-serialization of DecryptedMessage type, encrypted with a key generated during chat initialization |
| file | InputEncryptedFile | File attachment for the secret chat |


## Result
messages.SentEncryptedMessage

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | DATA_TOO_LONG | Data too long. |
| 400 | ENCRYPTION_DECLINED | The secret chat was declined. |
| 400 | FILE_EMTPY | An empty file was provided. |
| 400 | MD5_CHECKSUM_INVALID | The MD5 checksums do not match. |
| 400 | MSG_WAIT_FAILED | A waiting call returned an error. |

