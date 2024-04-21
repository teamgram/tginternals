# messages.getStickerSet
Get info about a stickerset

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
messages.getStickerSet#c8a0ec74 stickerset:InputStickerSet hash:int = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stickerset | InputStickerSet | Stickerset |
| hash | int | Hash for pagination, for more info click here |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | EMOTICON_STICKERPACK_MISSING | inputStickerSetDice.emoji cannot be empty. |
| 406 | STICKERSET_INVALID | The provided sticker set is invalid. |

