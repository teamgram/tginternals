# messages.report
Report a message in a chat for violation of telegram's Terms of Service

```
reportResultChooseOption#f0e4e0b6 title:string options:Vector<MessageReportOption> = ReportResult;
reportResultAddComment#6f09ac31 flags:# optional:flags.0?true option:bytes = ReportResult;
reportResultReported#8db33c4b = ReportResult;
---functions---
messages.report#fc78af9b peer:InputPeer id:Vector<int> option:bytes message:string = ReportResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer |
| id | Vector<int> | IDs of messages to report |
| option | bytes | Menu option, intially empty |
| message | string | Comment for report moderation |


## Result
ReportResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | OPTION_INVALID | Invalid option selected. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

