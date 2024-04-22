# Messages.FeaturedStickers
Featured stickers

```
messages.featuredStickersNotModified#c6dc0c66 count:int = messages.FeaturedStickers;
messages.featuredStickers#be382906 flags:# premium:flags.0?true hash:long count:int sets:Vector<StickerSetCovered> unread:Vector<long> = messages.FeaturedStickers;

---functions---

messages.getFeaturedStickers#64780b14 hash:long = messages.FeaturedStickers;
messages.getOldFeaturedStickers#7ed094a1 offset:int limit:int hash:long = messages.FeaturedStickers;
messages.getFeaturedEmojiStickers#ecf6736 hash:long = messages.FeaturedStickers;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.featuredStickersNotModified | Featured stickers haven't changed |
| messages.featuredStickers | Featured stickersets |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getFeaturedStickers | Get featured stickers |
| messages.getOldFeaturedStickers | Method for fetching previously featured stickers |
| messages.getFeaturedEmojiStickers | Gets featured custom emoji stickersets. |


