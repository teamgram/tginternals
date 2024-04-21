# account.checkUsername
Validates a username and checks availability.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.checkUsername#2714d86c username:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| username | string | usernameAccepted characters: A-z (case-insensitive), 0-9 and underscores.Length: 5-32 characters. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USERNAME_INVALID | The provided username is not valid. |
| 400 | USERNAME_OCCUPIED | The provided username is already occupied. |
| 400 | USERNAME_PURCHASE_AVAILABLE | The specified username can be purchased on https://fragment.com. |

