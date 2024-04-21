# decryptedMessage
Contents of an encrypted message.

```
===8===
decryptedMessage#1f814f1f random_id:long random_bytes:bytes message:string media:DecryptedMessageMedia = DecryptedMessage;

===17===
decryptedMessage#204d3878 random_id:long ttl:int message:string media:DecryptedMessageMedia = DecryptedMessage;

===45===
decryptedMessage#36b091de flags:# random_id:long ttl:int message:string media:flags.9?DecryptedMessageMedia entities:flags.7?Vector<MessageEntity> via_bot_name:flags.11?string reply_to_random_id:flags.3?long = DecryptedMessage;

===73===
decryptedMessage#91cc4674 flags:# no_webpage:flags.1?true silent:flags.5?true random_id:long ttl:int message:string media:flags.9?DecryptedMessageMedia entities:flags.7?Vector<MessageEntity> via_bot_name:flags.11?string reply_to_random_id:flags.3?long grouped_id:flags.17?long = DecryptedMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields (added in layer 45) |
| no_webpage | flags.1?true | Whether the webpage preview is disabled |
| silent | flags.5?true | Whether this is a silent message (no notification triggered) |
| random_id | long | Random message ID, assigned by the author of message.Must be equal to the ID passed to sending method. |
| ttl | int | Message lifetime. Has higher priority than decryptedMessageActionSetMessageTTL.Parameter added in Layer 17. |
| message | string | Message text |
| media | flags.9?DecryptedMessageMedia | Media content |
| entities | flags.7?Vector<MessageEntity> | Message entities for styled text (parameter added in layer 45) |
| via_bot_name | flags.11?string | Specifies the ID of the inline bot that generated the message (parameter added in layer 45) |
| reply_to_random_id | flags.3?long | Random message ID of the message this message replies to (parameter added in layer 45) |
| grouped_id | flags.17?long | Random group ID, assigned by the author of message.Multiple encrypted messages with a photo attached and with the same group ID indicate an album or grouped media (parameter added in layer 45) |


## Type
DecryptedMessage

## Related pages
