# account.updateDeviceLocked
When client-side passcode lock feature is enabled, will not show message texts in incoming PUSH notifications.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.updateDeviceLocked#38df3532 period:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| period | int | Inactivity period after which to start hiding message texts in PUSH notifications. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

