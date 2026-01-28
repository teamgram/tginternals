# webPageAttributeStickerSet
Contains info about a stickerset », for a webPage preview of a stickerset deep link » (the webPage will have a type of telegram_stickerset).

```
webPageAttributeStickerSet#50cc03d3 flags:# emojis:flags.0?true text_color:flags.1?true stickers:Vector<Document> = WebPageAttribute;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| emojis | flags.0?true | Whether this i s a custom emoji stickerset. |
| text_color | flags.1?true | Whether the color of this TGS custom emoji stickerset should be changed to the text color when used in messages, the accent color if used as emoji status, white on chat photos, or another appropriate color based on context. |
| stickers | Vector<Document> | A subset of the stickerset in the stickerset. |


## Type
WebPageAttribute

## Related pages
