# account.getWallPaper
Get info about a certain wallpaper

```
wallPaper#a437c3ed id:long flags:# creator:flags.0?true default:flags.1?true pattern:flags.3?true dark:flags.4?true access_hash:long slug:string document:Document settings:flags.2?WallPaperSettings = WallPaper;
wallPaperNoFile#e0804116 id:long flags:# default:flags.1?true dark:flags.4?true settings:flags.2?WallPaperSettings = WallPaper;
---functions---
account.getWallPaper#fc8ddbea wallpaper:InputWallPaper = WallPaper;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| wallpaper | InputWallPaper | The wallpaper to get info about |


## Result
WallPaper

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | WALLPAPER_INVALID | The specified wallpaper is invalid. |

