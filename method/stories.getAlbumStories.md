# stories.getAlbumStories
Get stories in a story album ».

```
stories.stories#63c3dd0a flags:# count:int stories:Vector<StoryItem> pinned_to_top:flags.0?Vector<int> chats:Vector<Chat> users:Vector<User> = stories.Stories;
---functions---
stories.getAlbumStories#ac806d61 peer:InputPeer album_id:int offset:int limit:int = stories.Stories;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the album is posted. |
| album_id | int | ID of the album. |
| offset | int | Offset for pagination. |
| limit | int | Maximum number of results to return, see pagination |


## Result
stories.Stories

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

