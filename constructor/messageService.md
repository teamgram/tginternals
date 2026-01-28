# messageService
Indicates a service message

```
messageService#7a800e0a flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true reactions_are_possible:flags.9?true silent:flags.13?true post:flags.14?true legacy:flags.19?true id:int from_id:flags.8?Peer peer_id:Peer saved_peer_id:flags.28?Peer reply_to:flags.3?MessageReplyHeader date:int action:MessageAction reactions:flags.20?MessageReactions ttl_period:flags.25?int = Message;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| out | flags.1?true | Whether the message is outgoing |
| mentioned | flags.4?true | Whether we were mentioned in the message |
| media_unread | flags.5?true | Whether the message contains unread media |
| reactions_are_possible | flags.9?true | Whether you can react to this message ». |
| silent | flags.13?true | Whether the message is silent |
| post | flags.14?true | Whether it's a channel post |
| legacy | flags.19?true | This is a legacy message: it has to be refetched with the new layer |
| id | int | Message ID |
| from_id | flags.8?Peer | ID of the sender of this message |
| peer_id | Peer | Sender of service message |
| saved_peer_id | flags.28?Peer | Will only be set for service messages within a monoforum topic »: peer will be equal to the ID of the monoforum and the saved_peer_id flag will be set to the ID of a topic. |
| reply_to | flags.3?MessageReplyHeader | Reply (thread) information |
| date | int | Message date |
| action | MessageAction | Event connected with the service message |
| reactions | flags.20?MessageReactions | Reactions ». |
| ttl_period | flags.25?int | Time To Live of the message, once message.date+message.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. |


## Type
Message

## Related pages
