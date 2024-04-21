# messages.getDialogs
Returns the current user dialog list.

```
messages.dialogs#15ba6c40 dialogs:Vector<Dialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Dialogs;
messages.dialogsSlice#71e094f3 count:int dialogs:Vector<Dialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Dialogs;
messages.dialogsNotModified#f0e3e596 count:int = messages.Dialogs;
---functions---
messages.getDialogs#a0f4cb4f flags:# exclude_pinned:flags.0?true folder_id:flags.1?int offset_date:int offset_id:int offset_peer:InputPeer limit:int hash:long = messages.Dialogs;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| exclude_pinned | flags.0?true | Exclude pinned dialogs |
| folder_id | flags.1?int | Peer folder ID, for more info click here |
| offset_date | int | Offsets for pagination, for more info click here |
| offset_id | int | Offsets for pagination, for more info click here (top_message ID used for pagination) |
| offset_peer | InputPeer | Offset peer for pagination |
| limit | int | Number of list elements to be returned |
| hash | long | Hash for pagination, for more info click here |


## Result
messages.Dialogs

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | FOLDER_ID_INVALID | Invalid folder ID. |
| 400 | OFFSET_PEER_ID_INVALID | The provided offset peer is invalid. |

