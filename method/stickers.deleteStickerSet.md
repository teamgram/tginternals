# stickers.deleteStickerSet
Deletes a stickerset we created, bots only.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stickers.deleteStickerSet#87704394 stickerset:InputStickerSet = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stickerset | InputStickerSet | Stickerset to delete |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_MISSING | Only bots can call this method, please use @stickers if you're a user. |
| 400 | STICKERSET_INVALID | The provided sticker set is invalid. |

