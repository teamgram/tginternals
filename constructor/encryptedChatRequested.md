# encryptedChatRequested
Request to create an encrypted chat.

```
encryptedChatRequested#48f1d94c flags:# folder_id:flags.0?int id:int access_hash:long date:int admin_id:long participant_id:long g_a:bytes = EncryptedChat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| folder_id | flags.0?int | Peer folder ID, for more info click here |
| id | int | Chat ID |
| access_hash | long | Check sum depending on user ID |
| date | int | Chat creation date |
| admin_id | long | Chat creator ID |
| participant_id | long | ID of second chat participant |
| g_a | bytes | A = g ^ a mod p, see Wikipedia |


## Type
EncryptedChat

## Related pages
