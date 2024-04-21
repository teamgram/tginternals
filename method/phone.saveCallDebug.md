# phone.saveCallDebug
Send phone call debug data to server

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
phone.saveCallDebug#277add7e peer:InputPhoneCall debug:DataJSON = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPhoneCall | Phone call |
| debug | DataJSON | Debug statistics obtained from libtgvoip |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CALL_PEER_INVALID | The provided call peer object is invalid. |
| 400 | DATA_JSON_INVALID | The provided JSON data is invalid. |

