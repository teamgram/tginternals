# messages.requestEncryption
Sends a request to start a secret chat to the user.

```
encryptedChatEmpty#ab7ec0a0 id:int = EncryptedChat;
encryptedChatWaiting#66b25953 id:int access_hash:long date:int admin_id:long participant_id:long = EncryptedChat;
encryptedChatRequested#48f1d94c flags:# folder_id:flags.0?int id:int access_hash:long date:int admin_id:long participant_id:long g_a:bytes = EncryptedChat;
encryptedChat#61f0d4c7 id:int access_hash:long date:int admin_id:long participant_id:long g_a_or_b:bytes key_fingerprint:long = EncryptedChat;
encryptedChatDiscarded#1e1c7c45 flags:# history_deleted:flags.0?true id:int = EncryptedChat;
---functions---
messages.requestEncryption#f64daf43 user_id:InputUser random_id:int g_a:bytes = EncryptedChat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | User ID |
| random_id | int | Unique client request ID required to prevent resending. This also doubles as the chat ID. |
| g_a | bytes | A = g ^ a mod p, see Wikipedia |


## Result
EncryptedChat

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DH_G_A_INVALID | g_a invalid. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

