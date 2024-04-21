# stickers.changeSticker
Update the keywords, emojis or mask coordinates of a sticker, bots only.

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
stickers.changeSticker#f5537ebc flags:# sticker:InputDocument emoji:flags.0?string mask_coords:flags.1?MaskCoords keywords:flags.2?string = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| sticker | InputDocument | The sticker |
| emoji | flags.0?string | If set, updates the emoji list associated to the sticker |
| mask_coords | flags.1?MaskCoords | If set, updates the mask coordinates |
| keywords | flags.2?string | If set, updates the sticker keywords (separated by commas). Can't be provided for mask stickers. |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_MISSING | Only bots can call this method, please use @stickers if you're a user. |
| 400 | STICKER_INVALID | The provided sticker is invalid. |

