# messages.getSearchCounters
Get the number of results that would be found by a messages.search call with the same parameters

```
---functions---
messages.getSearchCounters#1bbcf300 flags:# peer:InputPeer saved_peer_id:flags.2?InputPeer top_msg_id:flags.0?int filters:Vector<MessagesFilter> = Vector<messages.SearchCounter>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer where to search |
| saved_peer_id | flags.2?InputPeer | Search within the saved message dialog » with this ID. |
| top_msg_id | flags.0?int | If set, consider only messages within the specified forum topic |
| filters | Vector<MessagesFilter> | Search filters |


## Result
Vector<messages.SearchCounter>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

