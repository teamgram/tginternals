# stickerSet
Represents a stickerset (stickerpack)

```
stickerSet#2dd14edc flags:# archived:flags.1?true official:flags.2?true masks:flags.3?true animated:flags.5?true videos:flags.6?true emojis:flags.7?true text_color:flags.9?true channel_emoji_status:flags.10?true installed_date:flags.0?int id:long access_hash:long title:string short_name:string thumbs:flags.4?Vector<PhotoSize> thumb_dc_id:flags.4?int thumb_version:flags.4?int thumb_document_id:flags.8?long count:int hash:int = StickerSet;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| archived | flags.1?true | Whether this stickerset was archived (due to too many saved stickers in the current account) |
| official | flags.2?true | Is this stickerset official |
| masks | flags.3?true | Is this a mask stickerset |
| animated | flags.5?true | Is this an animated stickerpack |
| videos | flags.6?true | Is this a video stickerpack |
| emojis | flags.7?true | This is a custom emoji stickerset |
| text_color | flags.9?true | Whether the color of this TGS custom emoji stickerset should be changed to the text color when used in messages, the accent color if used as emoji status, white on chat photos, or another appropriate color based on context. |
| channel_emoji_status | flags.10?true | If set, this custom emoji stickerset can be used in channel emoji statuses. |
| installed_date | flags.0?int | When was this stickerset installed |
| id | long | ID of the stickerset |
| access_hash | long | Access hash of stickerset |
| title | string | Title of stickerset |
| short_name | string | Short name of stickerset, used when sharing stickerset using stickerset deep links. |
| thumbs | flags.4?Vector<PhotoSize> | Stickerset thumbnail |
| thumb_dc_id | flags.4?int | DC ID of thumbnail |
| thumb_version | flags.4?int | Thumbnail version |
| thumb_document_id | flags.8?long | Document ID of custom emoji thumbnail, fetch the document using messages.getCustomEmojiDocuments |
| count | int | Number of stickers in pack |
| hash | int | Hash |


## Type
StickerSet

## Related pages
