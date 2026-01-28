# StarGiftCollection
Represents a star gift collection ».

```
starGiftCollection#9d6b13b0 flags:# collection_id:int title:string icon:flags.0?Document gifts_count:int hash:long = StarGiftCollection;

---functions---

payments.createStarGiftCollection#1f4a0e87 peer:InputPeer title:string stargift:Vector<InputSavedStarGift> = StarGiftCollection;
payments.updateStarGiftCollection#4fddbee7 flags:# peer:InputPeer collection_id:int title:flags.0?string delete_stargift:flags.1?Vector<InputSavedStarGift> add_stargift:flags.2?Vector<InputSavedStarGift> order:flags.3?Vector<InputSavedStarGift> = StarGiftCollection;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| starGiftCollection | Represents a star gift collection ». |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.createStarGiftCollection | Create a star gift collection ». |
| payments.updateStarGiftCollection | Add or remove gifts from a star gift collection », or rename the collection. |


