# messages.Dialogs
Object contains a list of chats with messages and auxiliary data.

```
messages.dialogs#15ba6c40 dialogs:Vector<Dialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Dialogs;
messages.dialogsSlice#71e094f3 count:int dialogs:Vector<Dialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Dialogs;
messages.dialogsNotModified#f0e3e596 count:int = messages.Dialogs;

---functions---

messages.getDialogs#a0f4cb4f flags:# exclude_pinned:flags.0?true folder_id:flags.1?int offset_date:int offset_id:int offset_peer:InputPeer limit:int hash:long = messages.Dialogs;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.dialogs | Full list of chats with messages and auxiliary data. |
| messages.dialogsSlice | Incomplete list of dialogs with messages and auxiliary data. |
| messages.dialogsNotModified | Dialogs haven't changed |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getDialogs | Returns the current user dialog list. |


