# messages.SavedDialogs
Represents some saved message dialogs ».

```
messages.savedDialogs#f83ae221 dialogs:Vector<SavedDialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SavedDialogs;
messages.savedDialogsSlice#44ba9dd9 count:int dialogs:Vector<SavedDialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SavedDialogs;
messages.savedDialogsNotModified#c01f6fe8 count:int = messages.SavedDialogs;

---functions---

messages.getSavedDialogs#5381d21a flags:# exclude_pinned:flags.0?true offset_date:int offset_id:int offset_peer:InputPeer limit:int hash:long = messages.SavedDialogs;
messages.getPinnedSavedDialogs#d63d94e0 = messages.SavedDialogs;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.savedDialogs | Represents some saved message dialogs ». |
| messages.savedDialogsSlice | Incomplete list of saved message dialogs » with messages and auxiliary data. |
| messages.savedDialogsNotModified | The saved dialogs haven't changed |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getSavedDialogs | Returns the current saved dialog list, see here » for more info. |
| messages.getPinnedSavedDialogs | Get pinned saved dialogs, see here » for more info. |


