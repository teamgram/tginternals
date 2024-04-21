# stickers.renameStickerSet
Renames a stickerset, bots only.

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
stickers.renameStickerSet#124b1c00 stickerset:InputStickerSet title:string = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stickerset | InputStickerSet | Stickerset to rename |
| title | string | New stickerset title |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STICKERSET_INVALID | The provided sticker set is invalid. |

