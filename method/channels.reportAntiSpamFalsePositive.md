# channels.reportAntiSpamFalsePositive
Report a native antispam false positive

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.reportAntiSpamFalsePositive#a850a693 channel:InputChannel msg_id:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Supergroup ID |
| msg_id | int | Message ID that was mistakenly deleted by the native antispam system, taken from the admin log |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

