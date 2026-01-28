# payments.saveStarGift
Display or remove a received gift » from our profile.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.saveStarGift#2a2a697c flags:# unsave:flags.0?true stargift:InputSavedStarGift = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| unsave | flags.0?true | If set, hides the gift from our profile. |
| stargift | InputSavedStarGift | The gift to display or remove. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | SAVED_ID_EMPTY | The passed inputSavedStarGiftChat.saved_id is empty. |
| 400 | STARGIFT_OWNER_INVALID | You cannot transfer or sell a gift owned by another user. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

