# payments.reorderStarGiftCollections
Reorder the star gift collections » on an owned peer's profile.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.reorderStarGiftCollections#c32af4cc peer:InputPeer order:Vector<int> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The owned peer. |
| order | Vector<int> | New collection order. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

