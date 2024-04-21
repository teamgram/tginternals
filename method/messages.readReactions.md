# messages.readReactions
Mark message reactions » as read

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
---functions---
messages.readReactions#54aa7f8e flags:# peer:InputPeer top_msg_id:flags.0?int = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer |
| top_msg_id | flags.0?int | Mark as read only reactions to messages within the specified forum topic |


## Result
messages.AffectedHistory

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

