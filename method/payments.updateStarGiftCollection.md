# payments.updateStarGiftCollection
Add or remove gifts from a star gift collection », or rename the collection.

```
starGiftCollection#9d6b13b0 flags:# collection_id:int title:string icon:flags.0?Document gifts_count:int hash:long = StarGiftCollection;
---functions---
payments.updateStarGiftCollection#4fddbee7 flags:# peer:InputPeer collection_id:int title:flags.0?string delete_stargift:flags.1?Vector<InputSavedStarGift> add_stargift:flags.2?Vector<InputSavedStarGift> order:flags.3?Vector<InputSavedStarGift> = StarGiftCollection;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer that owns the collection. |
| collection_id | int | Collection ID. |
| title | flags.0?string | Title of the collection, to rename the collection. |
| delete_stargift | flags.1?Vector<InputSavedStarGift> | Can contain a list of gifts to remove from the collection. |
| add_stargift | flags.2?Vector<InputSavedStarGift> | Can contain a list of gifts to add to the collection. |
| order | flags.3?Vector<InputSavedStarGift> | Can contain the new gift order. |


## Result
StarGiftCollection

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

