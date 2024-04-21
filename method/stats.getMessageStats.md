# stats.getMessageStats
Get message statistics

```
stats.messageStats#7fe91c14 views_graph:StatsGraph reactions_by_emotion_graph:StatsGraph = stats.MessageStats;
---functions---
stats.getMessageStats#b6e0a3f5 flags:# dark:flags.0?true channel:InputChannel msg_id:int = stats.MessageStats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| dark | flags.0?true | Whether to enable dark theme for graph colors |
| channel | InputChannel | Channel ID |
| msg_id | int | Message ID |


## Result
stats.MessageStats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

