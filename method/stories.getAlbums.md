# stories.getAlbums
Get story albums created by a peer.

```
stories.albumsNotModified#564edaeb = stories.Albums;
stories.albums#c3987a3a hash:long albums:Vector<StoryAlbum> = stories.Albums;
---functions---
stories.getAlbums#25b3eac7 peer:InputPeer hash:long = stories.Albums;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer. |
| hash | long | The hash from a previously returned stories.albums, to avoid returning any results if they haven't changed. |


## Result
stories.Albums

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

