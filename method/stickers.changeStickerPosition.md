# stickers.changeStickerPosition
Changes the absolute position of a sticker in the set to which it belongs; for bots only. The sticker set must have been created by the bot

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
stickers.changeStickerPosition#ffb6d4ca sticker:InputDocument position:int = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| sticker | InputDocument | The sticker |
| position | int | The new position of the sticker, zero-based |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STICKER_INVALID | The provided sticker is invalid. |

