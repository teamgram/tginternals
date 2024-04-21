# messagePeerReaction
How a certain peer reacted to the message

```
messagePeerReaction#8c79b63c flags:# big:flags.0?true unread:flags.1?true my:flags.2?true peer_id:Peer date:int reaction:Reaction = MessagePeerReaction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| big | flags.0?true | Whether the specified message reaction » should elicit a bigger and longer reaction |
| unread | flags.1?true | Whether the reaction wasn't yet marked as read by the current user |
| my | flags.2?true | Starting from layer 159, messages.sendReaction will send reactions from the peer (user or channel) specified using messages.saveDefaultSendAs. If set, this flag indicates that this reaction was sent by us, even if the peer doesn't point to the current account. |
| peer_id | Peer | Peer that reacted to the message |
| date | int | When was this reaction added |
| reaction | Reaction | Reaction emoji |


## Type
MessagePeerReaction

## Related pages
