# stickers.addStickerToSet
Add a sticker to a stickerset, bots only. The sticker set must have been created by the bot.

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
stickers.addStickerToSet#8653febe stickerset:InputStickerSet sticker:InputStickerSetItem = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stickerset | InputStickerSet | The stickerset |
| sticker | InputStickerSetItem | The sticker |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_MISSING | Only bots can call this method, please use @stickers if you're a user. |
| 400 | STICKERPACK_STICKERS_TOO_MUCH | There are too many stickers in this stickerpack, you can't add any more. |
| 406 | STICKERSET_INVALID | The provided sticker set is invalid. |
| 400 | STICKERS_TOO_MUCH | There are too many stickers in this stickerpack, you can't add any more. |
| 400 | STICKER_PNG_NOPNG | One of the specified stickers is not a valid PNG file. |
| 400 | STICKER_TGS_NOTGS | Invalid TGS sticker provided. |

