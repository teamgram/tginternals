# messages.ChatFull
Full info about a channel, supergroup, gigagroup or basic group.

```
messages.chatFull#e5d7d19c full_chat:ChatFull chats:Vector<Chat> users:Vector<User> = messages.ChatFull;

---functions---

messages.getFullChat#aeb00b34 chat_id:long = messages.ChatFull;

channels.getFullChannel#8736a09 channel:InputChannel = messages.ChatFull;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.chatFull | Full info about a channel, supergroup, gigagroup or basic group. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getFullChat | Get full info about a basic group. |
| channels.getFullChannel | Get full info about a supergroup, gigagroup or channel |


