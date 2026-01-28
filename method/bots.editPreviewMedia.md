# bots.editPreviewMedia
Edit a main mini app preview, see here » for more info.

```
botPreviewMedia#23e91ba3 date:int media:MessageMedia = BotPreviewMedia;
---functions---
bots.editPreviewMedia#8525606f bot:InputUser lang_code:string media:InputMedia new_media:InputMedia = BotPreviewMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The bot that owns the Main Mini App. |
| lang_code | string | ISO 639-1 language code, indicating the localization of the preview to edit. |
| media | InputMedia | The photo/video preview to replace, previously fetched as specified here ». |
| new_media | InputMedia | The new photo/video preview, uploaded using messages.uploadMedia. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

