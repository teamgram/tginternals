# payments.savedStarGifts
Represents a list of gifts.

```
payments.savedStarGifts#95f389b1 flags:# count:int chat_notifications_enabled:flags.1?Bool gifts:Vector<SavedStarGift> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.SavedStarGifts;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of results (can be less than the returned gifts, in which case next_offset will be set). |
| chat_notifications_enabled | flags.1?Bool | Ternary value: can be not set, set&true, set&false. Can only be set for channels we own: the value indicates whether we enabled gift notifications for this channel. |
| gifts | Vector<SavedStarGift> | Gifts |
| next_offset | flags.0?string | Offset to pass to payments.getSavedStarGifts to fetch the next page of results. |
| chats | Vector<Chat> | Channels mentioned in gifts |
| users | Vector<User> | Users mentioned in gifts |


## Type
payments.SavedStarGifts

## Related pages
