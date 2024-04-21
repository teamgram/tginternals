# account.uploadTheme
Upload theme

```
documentEmpty#36f8c871 id:long = Document;
document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;
---functions---
account.uploadTheme#1c3db333 flags:# file:InputFile thumb:flags.0?InputFile file_name:string mime_type:string = Document;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| file | InputFile | Previously uploaded theme file with platform-specific colors for UI components, can be left unset when creating themes that only modify the wallpaper or accent colors. |
| thumb | flags.0?InputFile | Thumbnail |
| file_name | string | File name |
| mime_type | string | MIME type, must be application/x-tgtheme-{format}, where format depends on the client |


## Result
Document

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | THEME_FILE_INVALID | Invalid theme file provided. |

