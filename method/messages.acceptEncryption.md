# messages.acceptEncryption
Confirms creation of a secret chat

```
encryptedChatEmpty#ab7ec0a0 id:int = EncryptedChat;
encryptedChatWaiting#66b25953 id:int access_hash:long date:int admin_id:long participant_id:long = EncryptedChat;
encryptedChatRequested#48f1d94c flags:# folder_id:flags.0?int id:int access_hash:long date:int admin_id:long participant_id:long g_a:bytes = EncryptedChat;
encryptedChat#61f0d4c7 id:int access_hash:long date:int admin_id:long participant_id:long g_a_or_b:bytes key_fingerprint:long = EncryptedChat;
encryptedChatDiscarded#1e1c7c45 flags:# history_deleted:flags.0?true id:int = EncryptedChat;
---functions---
messages.acceptEncryption#3dbc0415 peer:InputEncryptedChat g_b:bytes key_fingerprint:long = EncryptedChat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputEncryptedChat | Secret chat ID |
| g_b | bytes | B = g ^ b mod p, see Wikipedia |
| key_fingerprint | long | 64-bit fingerprint of the received key |


## Result
EncryptedChat

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | ENCRYPTION_ALREADY_ACCEPTED | Secret chat already accepted. |
| 400 | ENCRYPTION_ALREADY_DECLINED | The secret chat was already declined. |

