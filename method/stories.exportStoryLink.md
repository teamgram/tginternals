# stories.exportStoryLink
Generate a story deep link for a specific story

```
exportedStoryLink#3fc9053b link:string = ExportedStoryLink;
---functions---
stories.exportStoryLink#7b8def20 peer:InputPeer id:int = ExportedStoryLink;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the story was posted |
| id | int | Story ID |


## Result
ExportedStoryLink

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORY_ID_EMPTY | You specified no story IDs. |
| 400 | USER_PUBLIC_MISSING | Cannot generate a link to stories posted by a peer without a username. |

