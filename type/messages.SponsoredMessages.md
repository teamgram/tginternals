# messages.SponsoredMessages
A set of sponsored messages associated with a channel

```
messages.sponsoredMessages#ffda656d flags:# posts_between:flags.0?int start_delay:flags.1?int between_delay:flags.2?int messages:Vector<SponsoredMessage> chats:Vector<Chat> users:Vector<User> = messages.SponsoredMessages;
messages.sponsoredMessagesEmpty#1839490f = messages.SponsoredMessages;

---functions---

messages.getSponsoredMessages#3d6ce850 flags:# peer:InputPeer msg_id:flags.0?int = messages.SponsoredMessages;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.sponsoredMessages | A set of sponsored messages associated to a channel |
| messages.sponsoredMessagesEmpty | No sponsored messages are available. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getSponsoredMessages | Get a list of sponsored messages for a peer, see here » for more info. |


