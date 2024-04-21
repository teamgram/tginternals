# messages.setBotCallbackAnswer
Set the callback answer to a user button press (bots only)

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setBotCallbackAnswer#d58f130a flags:# alert:flags.1?true query_id:long message:flags.0?string url:flags.2?string cache_time:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| alert | flags.1?true | Whether to show the message as a popup instead of a toast notification |
| query_id | long | Query ID |
| message | flags.0?string | Popup to show |
| url | flags.2?string | URL to open |
| cache_time | int | Cache validity |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_TOO_LONG | The provided message is too long. |
| 400 | QUERY_ID_INVALID | The query ID is invalid. |
| 400 | URL_INVALID | Invalid URL provided. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |

