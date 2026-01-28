# channels.setEmojiStickers
Set a custom emoji stickerset for supergroups. Only usable after reaching at least the boost level » specified in the group_emoji_stickers_level_min » config parameter.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.setEmojiStickers#3cd930b7 channel:InputChannel stickerset:InputStickerSet = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | The supergroup |
| stickerset | InputStickerSet | The custom emoji stickerset to associate to the supergroup |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |

