# stories.reorderAlbums
Reorder story albums on a profile ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stories.reorderAlbums#8535fbd9 peer:InputPeer order:Vector<int> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the albums are located. |
| order | Vector<int> | New order of the albums. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

