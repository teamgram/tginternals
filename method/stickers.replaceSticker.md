# stickers.replaceSticker
Replace a sticker in a stickerset ».

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
stickers.replaceSticker#4696459a sticker:InputDocument new_sticker:InputStickerSetItem = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| sticker | InputDocument | Old sticker document. |
| new_sticker | InputStickerSetItem | New sticker. |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STICKER_INVALID | The provided sticker is invalid. |

