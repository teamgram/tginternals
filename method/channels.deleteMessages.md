# channels.deleteMessages
Delete messages in a channel/supergroup

```
messages.affectedMessages#84d19185 pts:int pts_count:int = messages.AffectedMessages;
---functions---
channels.deleteMessages#84c1fd4e channel:InputChannel id:Vector<int> = messages.AffectedMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Channel/supergroup |
| id | Vector<int> | IDs of messages to delete |


## Result
messages.AffectedMessages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | MESSAGE_DELETE_FORBIDDEN | You can't delete one of the messages you tried to delete, most likely because it is a service message. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |

