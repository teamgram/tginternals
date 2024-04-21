# messages.deleteMessages
Deletes messages by their identifiers.

```
messages.affectedMessages#84d19185 pts:int pts_count:int = messages.AffectedMessages;
---functions---
messages.deleteMessages#e58e95d2 flags:# revoke:flags.0?true id:Vector<int> = messages.AffectedMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoke | flags.0?true | Whether to delete messages for all participants of the chat |
| id | Vector<int> | Message ID list |


## Result
messages.AffectedMessages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | MESSAGE_DELETE_FORBIDDEN | You can't delete one of the messages you tried to delete, most likely because it is a service message. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |

