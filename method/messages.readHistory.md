# messages.readHistory
Marks message history as read.

```
messages.affectedMessages#84d19185 pts:int pts_count:int = messages.AffectedMessages;
---functions---
messages.readHistory#e306d3a peer:InputPeer max_id:int = messages.AffectedMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Target user or group |
| max_id | int | If a positive value is passed, only messages with identifiers less or equal than the given one will be read |


## Result
messages.AffectedMessages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

