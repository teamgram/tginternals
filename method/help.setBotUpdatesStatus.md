# help.setBotUpdatesStatus
Informs the server about the number of pending bot updates if they haven't been processed for a long time; for bots only

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
help.setBotUpdatesStatus#ec22cfcd pending_updates_count:int message:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| pending_updates_count | int | Number of pending updates |
| message | string | Error message, if present |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

