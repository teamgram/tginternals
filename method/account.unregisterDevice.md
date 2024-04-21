# account.unregisterDevice
Deletes a device by its token, stops sending PUSH-notifications to it.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.unregisterDevice#6a0d3206 token_type:int token:string other_uids:Vector<long> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| token_type | int | Device token type, see PUSH updates for the possible values. |
| token | string | Device token, see PUSH updates for the possible values. |
| other_uids | Vector<long> | List of user identifiers of other users currently using the client |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | TOKEN_INVALID | The provided token is invalid. |

