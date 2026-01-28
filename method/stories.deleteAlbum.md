# stories.deleteAlbum
Delete a story album.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stories.deleteAlbum#8d3456d0 peer:InputPeer album_id:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Owned peer where the album is located. |
| album_id | int | ID of the album to delete. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

