# stickers.createStickerSet
Create a stickerset, bots only.

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;
---functions---
stickers.createStickerSet#9021ab67 flags:# masks:flags.0?true animated:flags.1?true videos:flags.4?true emojis:flags.5?true text_color:flags.6?true user_id:InputUser title:string short_name:string thumb:flags.2?InputDocument stickers:Vector<InputStickerSetItem> software:flags.3?string = messages.StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| masks | flags.0?true | Whether this is a mask stickerset |
| animated | flags.1?true | Whether this is an animated stickerset |
| videos | flags.4?true | Whether this is a video stickerset |
| emojis | flags.5?true | Whether this is a custom emoji stickerset. |
| text_color | flags.6?true | Whether the color of TGS custom emojis contained in this set should be changed to the text color when used in messages, the accent color if used as emoji status, white on chat photos, or another appropriate color based on context. For custom emoji stickersets only. |
| user_id | InputUser | Stickerset owner |
| title | string | Stickerset name, 1-64 chars |
| short_name | string | Short name of sticker set, to be used in sticker deep links ». Can contain only english letters, digits and underscores. Must begin with a letter, can't contain consecutive underscores and, if called by a bot, must end in "_by_<bot_username>". <bot_username> is case insensitive. 1-64 characters. |
| thumb | flags.2?InputDocument | Thumbnail |
| stickers | Vector<InputStickerSetItem> | Stickers |
| software | flags.3?string | Used when importing stickers using the sticker import SDKs, specifies the name of the software that created the stickers |


## Result
messages.StickerSet

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PACK_SHORT_NAME_INVALID | Short pack name invalid. |
| 400 | PACK_SHORT_NAME_OCCUPIED | A stickerpack with this name already exists. |
| 400 | PACK_TITLE_INVALID | The stickerpack title is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STICKERS_EMPTY | No sticker provided. |
| 400 | STICKER_EMOJI_INVALID | Sticker emoji invalid. |
| 400 | STICKER_FILE_INVALID | Sticker file invalid. |
| 400 | STICKER_GIF_DIMENSIONS | The specified video sticker has invalid dimensions. |
| 400 | STICKER_PNG_DIMENSIONS | Sticker png dimensions invalid. |
| 400 | STICKER_PNG_NOPNG | One of the specified stickers is not a valid PNG file. |
| 400 | STICKER_TGS_NODOC | You must send the animated sticker as a document. |
| 400 | STICKER_TGS_NOTGS | Invalid TGS sticker provided. |
| 400 | STICKER_THUMB_PNG_NOPNG | Incorrect stickerset thumb file provided, PNG / WEBP expected. |
| 400 | STICKER_THUMB_TGS_NOTGS | Incorrect stickerset TGS thumb file provided. |
| 400 | STICKER_VIDEO_BIG | The specified video sticker is too big. |
| 400 | STICKER_VIDEO_NODOC | You must send the video sticker as a document. |
| 400 | STICKER_VIDEO_NOWEBM | The specified video sticker is not in webm format. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

