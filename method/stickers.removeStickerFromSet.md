# stickers.removeStickerFromSet
Remove a sticker from the set where it belongs, bots only. The sticker set must have been created by the bot.

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
stickers.removeStickerFromSet#f7760f51 sticker:InputDocument = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| sticker | InputDocument | The sticker to remove |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_MISSING | Only bots can call this method, please use @stickers if you're a user. |
| 400 | STICKER_INVALID | The provided sticker is invalid. |

