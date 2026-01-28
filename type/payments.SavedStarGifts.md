# payments.SavedStarGifts
Represents a list of gifts.

```
payments.savedStarGifts#95f389b1 flags:# count:int chat_notifications_enabled:flags.1?Bool gifts:Vector<SavedStarGift> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.SavedStarGifts;

---functions---

payments.getSavedStarGifts#a319e569 flags:# exclude_unsaved:flags.0?true exclude_saved:flags.1?true exclude_unlimited:flags.2?true exclude_unique:flags.4?true sort_by_value:flags.5?true exclude_upgradable:flags.7?true exclude_unupgradable:flags.8?true peer:InputPeer collection_id:flags.6?int offset:string limit:int = payments.SavedStarGifts;
payments.getSavedStarGift#b455a106 stargift:Vector<InputSavedStarGift> = payments.SavedStarGifts;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.savedStarGifts | Represents a list of gifts. |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getSavedStarGifts | Fetch the full list of gifts owned by a peer.Note that unlike what the name suggests, the method can be used to fetch both "saved" and "unsaved" gifts (aka gifts both pinned and not pinned) to the profile, depending on the passed flags. |
| payments.getSavedStarGift | Fetch info about specific gifts owned by a peer we control.Note that unlike what the name suggests, the method can be used to fetch both "saved" and "unsaved" gifts (aka gifts both pinned and not pinned to the profile). |


