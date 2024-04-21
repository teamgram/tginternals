# encryptedChat
Encrypted chat

```
encryptedChat#61f0d4c7 id:int access_hash:long date:int admin_id:long participant_id:long g_a_or_b:bytes key_fingerprint:long = EncryptedChat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | int | Chat ID |
| access_hash | long | Check sum dependent on the user ID |
| date | int | Date chat was created |
| admin_id | long | Chat creator ID |
| participant_id | long | ID of the second chat participant |
| g_a_or_b | bytes | B = g ^ b mod p, if the currently authorized user is the chat's creator,or A = g ^ a mod p otherwiseSee Wikipedia for more info |
| key_fingerprint | long | 64-bit fingerprint of received key |


## Type
EncryptedChat

## Related pages
