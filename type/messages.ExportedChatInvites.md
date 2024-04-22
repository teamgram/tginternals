# messages.ExportedChatInvites
Info about chat invites exported by a certain admin.

```
messages.exportedChatInvites#bdc62dcc count:int invites:Vector<ExportedChatInvite> users:Vector<User> = messages.ExportedChatInvites;

---functions---

messages.getExportedChatInvites#a2b5a3f6 flags:# revoked:flags.3?true peer:InputPeer admin_id:InputUser offset_date:flags.2?int offset_link:flags.2?string limit:int = messages.ExportedChatInvites;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.exportedChatInvites | Info about chat invites exported by a certain admin. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getExportedChatInvites | Get info about the chat invites of a specific chat |


