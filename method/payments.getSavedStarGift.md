# payments.getSavedStarGift
Fetch info about specific gifts owned by a peer we control.

```
payments.savedStarGifts#95f389b1 flags:# count:int chat_notifications_enabled:flags.1?Bool gifts:Vector<SavedStarGift> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.SavedStarGifts;
---functions---
payments.getSavedStarGift#b455a106 stargift:Vector<InputSavedStarGift> = payments.SavedStarGifts;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stargift | Vector<InputSavedStarGift> | List of gifts to fetch info about. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SAVED_ID_EMPTY | The passed inputSavedStarGiftChat.saved_id is empty. |
| 400 | STARGIFT_SLUG_INVALID | The specified gift slug is invalid. |

