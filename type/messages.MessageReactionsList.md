# messages.MessageReactionsList
List of peers that reacted to a specific message

```
messages.messageReactionsList#31bd492d flags:# count:int reactions:Vector<MessagePeerReaction> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = messages.MessageReactionsList;

---functions---

messages.getMessageReactionsList#461b3f48 flags:# peer:InputPeer id:int reaction:flags.0?Reaction offset:flags.1?string limit:int = messages.MessageReactionsList;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.messageReactionsList | List of peers that reacted to a specific message |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getMessageReactionsList | Get message reaction list, along with the sender of each reaction. |


