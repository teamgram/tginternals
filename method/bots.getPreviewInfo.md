# bots.getPreviewInfo
Bot owners only, fetch main mini app preview information, see here » for more info.

```
bots.previewInfo#ca71d64 media:Vector<BotPreviewMedia> lang_codes:Vector<string> = bots.PreviewInfo;
---functions---
bots.getPreviewInfo#423ab3ad bot:InputUser lang_code:string = bots.PreviewInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The bot that owns the Main Mini App. |
| lang_code | string | Fetch previews for the specified ISO 639-1 language code. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

