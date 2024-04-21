# messages.deletePhoneCallHistory
Delete the entire phone call history.

```
messages.affectedFoundMessages#ef8d3e6c pts:int pts_count:int offset:int messages:Vector<int> = messages.AffectedFoundMessages;
---functions---
messages.deletePhoneCallHistory#f9cbe409 flags:# revoke:flags.0?true = messages.AffectedFoundMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoke | flags.0?true | Whether to remove phone call history for participants as well |


## Result
messages.AffectedFoundMessages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

