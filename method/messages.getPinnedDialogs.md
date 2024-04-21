# messages.getPinnedDialogs
Get pinned dialogs

```
messages.peerDialogs#3371c354 dialogs:Vector<Dialog> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> state:updates.State = messages.PeerDialogs;
---functions---
messages.getPinnedDialogs#d6b94df2 folder_id:int = messages.PeerDialogs;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| folder_id | int | Peer folder ID, for more info click here |


## Result
messages.PeerDialogs

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FOLDER_ID_INVALID | Invalid folder ID. |

