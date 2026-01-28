# messages.getSavedDialogs
Returns the current saved dialog list » or monoforum topic list ».

```
messages.savedDialogs#f83ae221 dialogs:Vector<SavedDialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SavedDialogs;
messages.savedDialogsSlice#44ba9dd9 count:int dialogs:Vector<SavedDialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SavedDialogs;
messages.savedDialogsNotModified#c01f6fe8 count:int = messages.SavedDialogs;
---functions---
messages.getSavedDialogs#1e91fc99 flags:# exclude_pinned:flags.0?true parent_peer:flags.1?InputPeer offset_date:int offset_id:int offset_peer:InputPeer limit:int hash:long = messages.SavedDialogs;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| exclude_pinned | flags.0?true | Exclude pinned dialogs |
| parent_peer | flags.1?InputPeer | If set, fetches the topic list of the passed monoforum, otherwise fetches the saved dialog list. |
| offset_date | int | Offsets for pagination, for more info click here |
| offset_id | int | Offsets for pagination, for more info click here (top_message ID used for pagination) |
| offset_peer | InputPeer | Offset peer for pagination |
| limit | int | Number of list elements to be returned |
| hash | long | Hash used for caching, for more info click here |


## Result
messages.SavedDialogs

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

