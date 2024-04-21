# stories.incrementStoryViews
Increment the view counter of one or more stories.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stories.incrementStoryViews#b2028afb peer:InputPeer id:Vector<int> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the stories were posted. |
| id | Vector<int> | IDs of the stories (maximum 200 at a time). |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORY_ID_EMPTY | You specified no story IDs. |

