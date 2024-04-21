# stories.getStoriesArchive
Fetch the story archive » of a peer we control.

```
stories.stories#5dd8c3c8 count:int stories:Vector<StoryItem> chats:Vector<Chat> users:Vector<User> = stories.Stories;
---functions---
stories.getStoriesArchive#b4352016 peer:InputPeer offset_id:int limit:int = stories.Stories;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer whose archived stories should be fetched |
| offset_id | int | Offsets for pagination, for more info click here |
| limit | int | Maximum number of results to return, see pagination |


## Result
stories.Stories

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

