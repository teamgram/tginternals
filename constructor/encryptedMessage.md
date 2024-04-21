# encryptedMessage
Encrypted message.

```
encryptedMessage#ed18c118 random_id:long chat_id:int date:int bytes:bytes file:EncryptedFile = EncryptedMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| random_id | long | Random message ID, assigned by the author of message |
| chat_id | int | ID of encrypted chat |
| date | int | Date of sending |
| bytes | bytes | TL-serialization of DecryptedMessage type, encrypted with the key created at chat initialization |
| file | EncryptedFile | Attached encrypted file |


## Type
EncryptedMessage

## Related pages
