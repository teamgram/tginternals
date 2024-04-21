# account.toggleUsername
Activate or deactivate a purchased fragment.com username associated to the currently logged-in user.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.toggleUsername#58d6b376 username:string active:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| username | string | Username |
| active | Bool | Whether to activate or deactivate it |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USERNAMES_ACTIVE_TOO_MUCH | The maximum number of active usernames was reached. |
| 400 | USERNAME_INVALID | The provided username is not valid. |

