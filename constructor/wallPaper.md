# wallPaper
Represents a wallpaper based on an image.

```
wallPaper#a437c3ed id:long flags:# creator:flags.0?true default:flags.1?true pattern:flags.3?true dark:flags.4?true access_hash:long slug:string document:Document settings:flags.2?WallPaperSettings = WallPaper;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | Identifier |
| flags | # | Flags, see TL conditional fields |
| creator | flags.0?true | Whether we created this wallpaper |
| default | flags.1?true | Whether this is the default wallpaper |
| pattern | flags.3?true | Whether this is a pattern wallpaper » |
| dark | flags.4?true | Whether this wallpaper should be used in dark mode. |
| access_hash | long | Access hash |
| slug | string | Unique wallpaper ID, used when generating wallpaper links or importing wallpaper links. |
| document | Document | The actual wallpaper |
| settings | flags.2?WallPaperSettings | Info on how to generate the wallpaper, according to these instructions ». |


## Type
WallPaper

## Related pages
