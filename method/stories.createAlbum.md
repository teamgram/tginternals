# stories.createAlbum
Creates a story album.

```
storyAlbum#9325705a flags:# album_id:int title:string icon_photo:flags.0?Photo icon_video:flags.1?Document = StoryAlbum;
---functions---
stories.createAlbum#a36396e5 peer:InputPeer title:string stories:Vector<int> = StoryAlbum;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The owned peer where to create the album. |
| title | string | Album name. |
| stories | Vector<int> | Stories to add to the album. |


## Result
StoryAlbum

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

