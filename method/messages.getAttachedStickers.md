# messages.getAttachedStickers
Get stickers attached to a photo or video

```
---functions---
messages.getAttachedStickers#cc5b67cc media:InputStickeredMedia = Vector<StickerSetCovered>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| media | InputStickeredMedia | Stickered media |


## Result
Vector<StickerSetCovered>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MEDIA_EMPTY | The provided media object is invalid. |

