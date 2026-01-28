# messages.getSavedDialogsByID
Obtain information about specific saved message dialogs » or monoforum topics ».

```
messages.savedDialogs#f83ae221 dialogs:Vector<SavedDialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SavedDialogs;
messages.savedDialogsSlice#44ba9dd9 count:int dialogs:Vector<SavedDialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SavedDialogs;
messages.savedDialogsNotModified#c01f6fe8 count:int = messages.SavedDialogs;
---functions---
messages.getSavedDialogsByID#6f6f9c96 flags:# parent_peer:flags.1?InputPeer ids:Vector<InputPeer> = messages.SavedDialogs;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| parent_peer | flags.1?InputPeer | If set, fetches monoforum topics », otherwise fetches saved message dialogs ». |
| ids | Vector<InputPeer> | IDs of dialogs (topics) to fetch. |


## Result
messages.SavedDialogs

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

