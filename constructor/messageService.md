# messageService
Indicates a service message

```
messageService#2b085862 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true legacy:flags.19?true id:int from_id:flags.8?Peer peer_id:Peer reply_to:flags.3?MessageReplyHeader date:int action:MessageAction ttl_period:flags.25?int = Message;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| out | flags.1?true | Whether the message is outgoing |
| mentioned | flags.4?true | Whether we were mentioned in the message |
| media_unread | flags.5?true | Whether the message contains unread media |
| silent | flags.13?true | Whether the message is silent |
| post | flags.14?true | Whether it's a channel post |
| legacy | flags.19?true | This is a legacy message: it has to be refetched with the new layer |
| id | int | Message ID |
| from_id | flags.8?Peer | ID of the sender of this message |
| peer_id | Peer | Sender of service message |
| reply_to | flags.3?MessageReplyHeader | Reply (thread) information |
| date | int | Message date |
| action | MessageAction | Event connected with the service message |
| ttl_period | flags.25?int | Time To Live of the message, once message.date+message.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. |


## Type
Message

## Related pages
