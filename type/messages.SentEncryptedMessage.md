# Messages.SentEncryptedMessage
Contains info on message sent to an encrypted chat.

```
messages.sentEncryptedMessage#560f8935 date:int = messages.SentEncryptedMessage;
messages.sentEncryptedFile#9493ff32 date:int file:EncryptedFile = messages.SentEncryptedMessage;

---functions---

messages.sendEncrypted#44fa7a15 flags:# silent:flags.0?true peer:InputEncryptedChat random_id:long data:bytes = messages.SentEncryptedMessage;
messages.sendEncryptedFile#5559481d flags:# silent:flags.0?true peer:InputEncryptedChat random_id:long data:bytes file:InputEncryptedFile = messages.SentEncryptedMessage;
messages.sendEncryptedService#32d439a4 peer:InputEncryptedChat random_id:long data:bytes = messages.SentEncryptedMessage;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.sentEncryptedMessage | Message without file attachments sent to an encrypted file. |
| messages.sentEncryptedFile | Message with a file enclosure sent to a protected chat |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.sendEncrypted | Sends a text message to a secret chat. |
| messages.sendEncryptedFile | Sends a message with a file attachment to a secret chat |
| messages.sendEncryptedService | Sends a service message to a secret chat. |


