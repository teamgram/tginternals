# stories.getStoryReactionsList
Get the reaction and interaction list of a story posted to a channel, along with the sender of each reaction.

```
stories.storyReactionsList#aa5f789c flags:# count:int reactions:Vector<StoryReaction> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryReactionsList;
---functions---
stories.getStoryReactionsList#b9b2881f flags:# forwards_first:flags.2?true peer:InputPeer id:int reaction:flags.0?Reaction offset:flags.1?string limit:int = stories.StoryReactionsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| forwards_first | flags.2?true | If set, returns forwards and reposts first, then reactions, then other views; otherwise returns interactions sorted just by interaction date. |
| peer | InputPeer | Channel |
| id | int | Story ID |
| reaction | flags.0?Reaction | Get only reactions of this type |
| offset | flags.1?string | Offset for pagination (taken from the next_offset field of the returned stories.StoryReactionsList); empty in the first request. |
| limit | int | Maximum number of results to return, see pagination |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

