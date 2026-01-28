# messages.deleteSavedHistory
Deletes messages from a monoforum topic », or deletes messages forwarded from a specific peer to saved messages ».

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
---functions---
messages.deleteSavedHistory#4dc5085f flags:# parent_peer:flags.0?InputPeer peer:InputPeer max_id:int min_date:flags.2?int max_date:flags.3?int = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| parent_peer | flags.0?InputPeer | If set, affects the messages of the passed monoforum topic », otherwise affects saved messages ». |
| peer | InputPeer | Peer, whose messages will be deleted from saved messages », or the ID of the topic. |
| max_id | int | Maximum ID of message to delete |
| min_date | flags.2?int | Delete all messages newer than this UNIX timestamp |
| max_date | flags.3?int | Delete all messages older than this UNIX timestamp |


## Result
messages.AffectedHistory

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

