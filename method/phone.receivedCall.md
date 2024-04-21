# phone.receivedCall
Optional: notify the server that the user is currently busy in a call: this will automatically refuse all incoming phone calls until the current phone call is ended.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
phone.receivedCall#17d54f61 peer:InputPhoneCall = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPhoneCall | The phone call we're currently in |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CALL_ALREADY_DECLINED | The call was already declined. |
| 400 | CALL_PEER_INVALID | The provided call peer object is invalid. |

