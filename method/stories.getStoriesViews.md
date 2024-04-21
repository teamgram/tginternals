# stories.getStoriesViews
Obtain info about the view count, forward count, reactions and recent viewers of one or more stories.

```
stories.storyViews#de9eed1d views:Vector<StoryViews> users:Vector<User> = stories.StoryViews;
---functions---
stories.getStoriesViews#28e16cc8 peer:InputPeer id:Vector<int> = stories.StoryViews;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer whose stories should be fetched |
| id | Vector<int> | Story IDs |


## Result
stories.StoryViews

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORY_ID_EMPTY | You specified no story IDs. |

