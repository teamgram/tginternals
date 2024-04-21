# account.uploadWallPaper
Create and upload a new wallpaper

```
wallPaper#a437c3ed id:long flags:# creator:flags.0?true default:flags.1?true pattern:flags.3?true dark:flags.4?true access_hash:long slug:string document:Document settings:flags.2?WallPaperSettings = WallPaper;
wallPaperNoFile#e0804116 id:long flags:# default:flags.1?true dark:flags.4?true settings:flags.2?WallPaperSettings = WallPaper;
---functions---
account.uploadWallPaper#e39a8f03 flags:# for_chat:flags.0?true file:InputFile mime_type:string settings:WallPaperSettings = WallPaper;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| for_chat | flags.0?true | Set this flag when uploading wallpapers to be passed to messages.setChatWallPaper. |
| file | InputFile | The JPG/PNG wallpaper |
| mime_type | string | MIME type of uploaded wallpaper |
| settings | WallPaperSettings | Wallpaper settings |


## Result
WallPaper

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | WALLPAPER_FILE_INVALID | The specified wallpaper file is invalid. |
| 400 | WALLPAPER_MIME_INVALID | The specified wallpaper MIME type is invalid. |

