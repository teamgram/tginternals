# stories.report
Report a story.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stories.report#1923fa8c peer:InputPeer id:Vector<int> reason:ReportReason message:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer that uploaded the story. |
| id | Vector<int> | IDs of the stories to report. |
| reason | ReportReason | Why are these storeis being reported. |
| message | string | Comment for report moderation |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

