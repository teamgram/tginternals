# messages.getMessageEditData
Find out if a media message's caption can be edited

```
messages.messageEditData#26b5dde6 flags:# caption:flags.0?true = messages.MessageEditData;
---functions---
messages.getMessageEditData#fda68d36 peer:InputPeer id:int = messages.MessageEditData;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the media was sent |
| id | int | ID of message |


## Result
messages.MessageEditData

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 403 | MESSAGE_AUTHOR_REQUIRED | Message author required. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

