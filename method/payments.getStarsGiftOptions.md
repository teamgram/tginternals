# payments.getStarsGiftOptions
Obtain a list of Telegram Stars gift options » as starsGiftOption constructors.

```
---functions---
payments.getStarsGiftOptions#d3c96bc8 flags:# user_id:flags.0?InputUser = Vector<StarsGiftOption>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| user_id | flags.0?InputUser | Receiver of the gift (optional). |


## Result
Vector<StarsGiftOption>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | USER_GIFT_UNAVAILABLE | Gifts are not available in the current region (stars_gifts_enabled is equal to false). |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

