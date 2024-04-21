# messages.messageReactionsList
List of peers that reacted to a specific message

```
messages.messageReactionsList#31bd492d flags:# count:int reactions:Vector<MessagePeerReaction> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = messages.MessageReactionsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of reactions matching query |
| reactions | Vector<MessagePeerReaction> | List of peers that reacted to a specific message |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |
| next_offset | flags.0?string | If set, indicates the next offset to use to load more results by invoking messages.getMessageReactionsList. |


## Type
messages.MessageReactionsList

## Related pages
