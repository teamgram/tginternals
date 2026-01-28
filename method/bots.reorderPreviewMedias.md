# bots.reorderPreviewMedias
Reorder a main mini app previews, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.reorderPreviewMedias#b627f3aa bot:InputUser lang_code:string order:Vector<InputMedia> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The bot that owns the Main Mini App. |
| lang_code | string | ISO 639-1 language code, indicating the localization of the previews to reorder. |
| order | Vector<InputMedia> | New order of the previews. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

