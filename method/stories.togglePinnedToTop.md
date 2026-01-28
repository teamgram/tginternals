# stories.togglePinnedToTop
Pin some stories to the top of the profile, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stories.togglePinnedToTop#b297e9b peer:InputPeer id:Vector<int> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where to pin stories. |
| id | Vector<int> | IDs of the stories to pin (max stories_pinned_to_top_count_max). |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORY_ID_INVALID | The specified story ID is invalid. |

