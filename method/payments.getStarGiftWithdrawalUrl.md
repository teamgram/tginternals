# payments.getStarGiftWithdrawalUrl
Convert a collectible gift » to an NFT on the TON blockchain.

```
payments.starGiftWithdrawalUrl#84aa3a9c url:string = payments.StarGiftWithdrawalUrl;
---functions---
payments.getStarGiftWithdrawalUrl#d06e93a8 stargift:InputSavedStarGift password:InputCheckPasswordSRP = payments.StarGiftWithdrawalUrl;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stargift | InputSavedStarGift | The collectible gift to export. |
| password | InputCheckPasswordSRP | The current user's 2FA password, passed as specified here ». |


## Result
payments.StarGiftWithdrawalUrl

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_HASH_INVALID | The provided password hash is invalid. |
| 400 | PASSWORD_TOO_FRESH_%d | The password was modified less than 24 hours ago, try again in %d seconds. |
| 400 | SESSION_TOO_FRESH_%d | This session was created less than 24 hours ago, try again in %d seconds. |

