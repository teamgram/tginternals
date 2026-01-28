# bots.deletePreviewMedia
Delete a main mini app preview, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.deletePreviewMedia#2d0135b3 bot:InputUser lang_code:string media:Vector<InputMedia> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The bot that owns the Main Mini App. |
| lang_code | string | ISO 639-1 language code, indicating the localization of the preview to delete. |
| media | Vector<InputMedia> | The photo/video preview to delete, previously fetched as specified here ». |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

