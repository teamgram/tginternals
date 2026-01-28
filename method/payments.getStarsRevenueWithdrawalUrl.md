# payments.getStarsRevenueWithdrawalUrl
Withdraw funds from a channel or bot's star balance ».

```
payments.starsRevenueWithdrawalUrl#1dab80b7 url:string = payments.StarsRevenueWithdrawalUrl;
---functions---
payments.getStarsRevenueWithdrawalUrl#2433dc92 flags:# ton:flags.0?true peer:InputPeer amount:flags.1?long password:InputCheckPasswordSRP = payments.StarsRevenueWithdrawalUrl;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| ton | flags.0?true | If set, withdraws channel/ad revenue in TON. |
| peer | InputPeer | Channel or bot from which to withdraw funds. |
| amount | flags.1?long | The amount of stars or nanotons to withdraw. |
| password | InputCheckPasswordSRP | 2FA password, see here » for more info. |


## Result
payments.StarsRevenueWithdrawalUrl

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_HASH_INVALID | The provided password hash is invalid. |
| 400 | PASSWORD_MISSING | You must enable 2FA before executing this operation. |
| 400 | PASSWORD_TOO_FRESH_%d | The password was modified less than 24 hours ago, try again in %d seconds. |
| 400 | SESSION_TOO_FRESH_%d | This session was created less than 24 hours ago, try again in %d seconds. |

