# account.deleteAccount
Delete the user's account from the telegram servers.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.deleteAccount#a2c0cf74 flags:# reason:string password:flags.0?InputCheckPasswordSRP = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| reason | string | Why is the account being deleted, can be empty |
| password | flags.0?InputCheckPasswordSRP | 2FA password: this field can be omitted even for accounts with 2FA enabled: in this case account account deletion will be delayed by 7 days as specified in the docs » |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 420 | 2FA_CONFIRM_WAIT_%d | Since this account is active and protected by a 2FA password, we will delete it in 1 week for security purposes. You can cancel this process at any time, you'll be able to reset your account in %d seconds. |

