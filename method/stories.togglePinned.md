# stories.togglePinned
Pin or unpin one or more stories

```
---functions---
stories.togglePinned#9a75a1ef peer:InputPeer id:Vector<int> pinned:Bool = Vector<int>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where to pin or unpin stories |
| id | Vector<int> | IDs of stories to pin or unpin |
| pinned | Bool | Whether to pin or unpin the stories |


## Result
Vector<int>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

