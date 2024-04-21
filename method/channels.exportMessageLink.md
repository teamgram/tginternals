# channels.exportMessageLink
Get link and embed info of a message in a channel/supergroup

```
exportedMessageLink#5dab1af4 link:string html:string = ExportedMessageLink;
---functions---
channels.exportMessageLink#e63fadeb flags:# grouped:flags.0?true thread:flags.1?true channel:InputChannel id:int = ExportedMessageLink;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| grouped | flags.0?true | Whether to include other grouped media (for albums) |
| thread | flags.1?true | Whether to also include a thread ID, if available, inside of the link |
| channel | InputChannel | Channel |
| id | int | Message ID |


## Result
ExportedMessageLink

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |

