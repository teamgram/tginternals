# stories.report
Report a story.

```
reportResultChooseOption#f0e4e0b6 title:string options:Vector<MessageReportOption> = ReportResult;
reportResultAddComment#6f09ac31 flags:# optional:flags.0?true option:bytes = ReportResult;
reportResultReported#8db33c4b = ReportResult;
---functions---
stories.report#19d8eb45 peer:InputPeer id:Vector<int> option:bytes message:string = ReportResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer that uploaded the story. |
| id | Vector<int> | IDs of the stories to report. |
| option | bytes | Menu option, intially empty |
| message | string | Comment for report moderation |


## Result
ReportResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

