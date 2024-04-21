# channels.clickSponsoredMessage
Informs the server that the user has either:

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.clickSponsoredMessage#18afbc93 channel:InputChannel random_id:bytes = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Channel where the sponsored message was posted |
| random_id | bytes | Message ID |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |

