# bots.sendCustomRequest
Sends a custom request; for bots only

```
dataJSON#7d748d04 data:string = DataJSON;
---functions---
bots.sendCustomRequest#aa2769ed custom_method:string params:DataJSON = DataJSON;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| custom_method | string | The method name |
| params | DataJSON | JSON-serialized method parameters |


## Result
DataJSON

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DATA_JSON_INVALID | The provided JSON data is invalid. |
| 400 | METHOD_INVALID | The specified method is invalid. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |

