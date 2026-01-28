# payments.convertStarGift
Convert a received gift » into Telegram Stars: this will permanently destroy the gift, converting it into starGift.convert_stars Telegram Stars, added to the user's balance.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.convertStarGift#74bf076b stargift:InputSavedStarGift = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stargift | InputSavedStarGift | The gift to convert. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | SAVED_ID_EMPTY | The passed inputSavedStarGiftChat.saved_id is empty. |
| 400 | STARGIFT_PEER_INVALID | The specified inputSavedStarGiftChat.peer is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

