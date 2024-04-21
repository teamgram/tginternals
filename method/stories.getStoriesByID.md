# stories.getStoriesByID
Obtain full info about a set of stories by their IDs.

```
stories.stories#5dd8c3c8 count:int stories:Vector<StoryItem> chats:Vector<Chat> users:Vector<User> = stories.Stories;
---functions---
stories.getStoriesByID#5774ca74 peer:InputPeer id:Vector<int> = stories.Stories;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the stories were posted |
| id | Vector<int> | Story IDs |


## Result
stories.Stories

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORIES_NEVER_CREATED | This peer hasn't ever posted any stories. |
| 400 | STORY_ID_EMPTY | You specified no story IDs. |

