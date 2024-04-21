# encryptedMessageService
Encrypted service message

```
encryptedMessageService#23734b06 random_id:long chat_id:int date:int bytes:bytes = EncryptedMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| random_id | long | Random message ID, assigned by the author of message |
| chat_id | int | ID of encrypted chat |
| date | int | Date of sending |
| bytes | bytes | TL-serialization of the DecryptedMessage type, encrypted with the key created at chat initialization |


## Type
EncryptedMessage

## Related pages
