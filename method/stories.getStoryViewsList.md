# stories.getStoryViewsList
Obtain the list of users that have viewed a specific story we posted

```
stories.storyViewsList#59d78fc5 flags:# count:int views_count:int forwards_count:int reactions_count:int views:Vector<StoryView> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryViewsList;
---functions---
stories.getStoryViewsList#7ed23c57 flags:# just_contacts:flags.0?true reactions_first:flags.2?true forwards_first:flags.3?true peer:InputPeer q:flags.1?string id:int offset:string limit:int = stories.StoryViewsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| just_contacts | flags.0?true | Whether to only fetch view reaction/views made by our contacts |
| reactions_first | flags.2?true | Whether to return storyView info about users that reacted to the story (i.e. if set, the server will first sort results by view date as usual, and then also additionally sort the list by putting storyViews with an associated reaction first in the list). Ignored if forwards_first is set. |
| forwards_first | flags.3?true | If set, returns forwards and reposts first, then reactions, then other views; otherwise returns interactions sorted just by interaction date. |
| peer | InputPeer | Peer where the story was posted |
| q | flags.1?string | Search for specific peers |
| id | int | Story ID |
| offset | string | Offset for pagination, obtained from stories.storyViewsList.next_offset |
| limit | int | Maximum number of results to return, see pagination |


## Result
stories.StoryViewsList

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORY_ID_INVALID | The specified story ID is invalid. |

