# messages.deleteSavedHistory
Deletes messages forwarded from a specific peer to saved messages ».

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
---functions---
messages.deleteSavedHistory#6e98102b flags:# peer:InputPeer max_id:int min_date:flags.2?int max_date:flags.3?int = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer, whose messages will be deleted from saved messages » |
| max_id | int | Maximum ID of message to delete |
| min_date | flags.2?int | Delete all messages newer than this UNIX timestamp |
| max_date | flags.3?int | Delete all messages older than this UNIX timestamp |


## Result
messages.AffectedHistory

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

