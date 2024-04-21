# stats.getStoryStats
Get statistics for a certain story.

```
stats.storyStats#50cd067c views_graph:StatsGraph reactions_by_emotion_graph:StatsGraph = stats.StoryStats;
---functions---
stats.getStoryStats#374fef40 flags:# dark:flags.0?true peer:InputPeer id:int = stats.StoryStats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| dark | flags.0?true | Whether to enable the dark theme for graph colors |
| peer | InputPeer | The peer that posted the story |
| id | int | Story ID |


## Result
stats.StoryStats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

