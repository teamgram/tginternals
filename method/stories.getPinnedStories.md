# stories.getPinnedStories
Fetch the stories pinned on a peer's profile.

```
stories.stories#63c3dd0a flags:# count:int stories:Vector<StoryItem> pinned_to_top:flags.0?Vector<int> chats:Vector<Chat> users:Vector<User> = stories.Stories;
---functions---
stories.getPinnedStories#5821a5dc peer:InputPeer offset_id:int limit:int = stories.Stories;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer whose pinned stories should be fetched |
| offset_id | int | Offsets for pagination, for more info click here |
| limit | int | Maximum number of results to return, see pagination |


## Result
stories.Stories

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

