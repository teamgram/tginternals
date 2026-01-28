# stories.updateAlbum
Rename a story albums », or add, delete or reorder stories in it.

```
storyAlbum#9325705a flags:# album_id:int title:string icon_photo:flags.0?Photo icon_video:flags.1?Document = StoryAlbum;
---functions---
stories.updateAlbum#5e5259b6 flags:# peer:InputPeer album_id:int title:flags.0?string delete_stories:flags.1?Vector<int> add_stories:flags.2?Vector<int> order:flags.3?Vector<int> = StoryAlbum;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer where the album is posted. |
| album_id | int | Album ID. |
| title | flags.0?string | New album title. |
| delete_stories | flags.1?Vector<int> | If set, deletes the specified stories from the album. |
| add_stories | flags.2?Vector<int> | If set, adds the specified stories to the album. |
| order | flags.3?Vector<int> | If set, reorders the stories in the album by their IDs. |


## Result
StoryAlbum

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

