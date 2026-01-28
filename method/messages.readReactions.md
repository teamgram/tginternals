# messages.readReactions
Mark message reactions » as read

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
---functions---
messages.readReactions#9ec44f93 flags:# peer:InputPeer top_msg_id:flags.0?int saved_peer_id:flags.1?InputPeer = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer |
| top_msg_id | flags.0?int | Mark as read only reactions to messages within the specified forum topic |
| saved_peer_id | flags.1?InputPeer | If set, must be equal to the ID of a monoforum topic: will affect that topic in the monoforum passed in peer. |


## Result
messages.AffectedHistory

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

