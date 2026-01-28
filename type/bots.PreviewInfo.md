# bots.PreviewInfo
Contains info about Main Mini App previews, see here » for more info.

```
bots.previewInfo#ca71d64 media:Vector<BotPreviewMedia> lang_codes:Vector<string> = bots.PreviewInfo;

---functions---

bots.getPreviewInfo#423ab3ad bot:InputUser lang_code:string = bots.PreviewInfo;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| bots.previewInfo | Contains info about Main Mini App previews, see here » for more info. |


## Methods
| Method | Description |
| ---- | ----------- |
| bots.getPreviewInfo | Bot owners only, fetch main mini app preview information, see here » for more info.Note: technically non-owners may also invoke this method, but it will always behave exactly as bots.getPreviewMedias, returning only previews for the current language and an empty lang_codes array, regardless of the passed lang_code, so please only use bots.getPreviewMedias if you're not the owner of the bot. |


