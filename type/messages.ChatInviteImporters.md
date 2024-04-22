# messages.ChatInviteImporters
List of users that imported a chat invitation link.

```
messages.chatInviteImporters#81b6b00a count:int importers:Vector<ChatInviteImporter> users:Vector<User> = messages.ChatInviteImporters;

---functions---

messages.getChatInviteImporters#df04dd4e flags:# requested:flags.0?true peer:InputPeer link:flags.1?string q:flags.2?string offset_date:int offset_user:InputUser limit:int = messages.ChatInviteImporters;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.chatInviteImporters | Info about the users that joined the chat using a specific chat invite |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getChatInviteImporters | Get info about the users that joined the chat using a specific chat invite |


