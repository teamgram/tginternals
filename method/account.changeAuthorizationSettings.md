# account.changeAuthorizationSettings
Change settings related to a session.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.changeAuthorizationSettings#40f48462 flags:# confirmed:flags.3?true hash:long encrypted_requests_disabled:flags.0?Bool call_requests_disabled:flags.1?Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| confirmed | flags.3?true | If set, confirms a newly logged in session ». |
| hash | long | Session ID from the authorization constructor, fetchable using account.getAuthorizations |
| encrypted_requests_disabled | flags.0?Bool | Whether to enable or disable receiving encrypted chats: if the flag is not set, the previous setting is not changed |
| call_requests_disabled | flags.1?Bool | Whether to enable or disable receiving calls: if the flag is not set, the previous setting is not changed |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | HASH_INVALID | The provided hash is invalid. |

