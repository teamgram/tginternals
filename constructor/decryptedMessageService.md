# decryptedMessageService
Contents of an encrypted service message.

```
===8===
decryptedMessageService#aa48327d random_id:long random_bytes:bytes action:DecryptedMessageAction = DecryptedMessage;

===17===
decryptedMessageService#73164160 random_id:long action:DecryptedMessageAction = DecryptedMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| random_id | long | Random message ID, assigned by the message author.Must be equal to the ID passed to the sending method. |
| action | DecryptedMessageAction | Action relevant to the service message |


## Type
DecryptedMessage

## Related pages
