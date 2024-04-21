# updatePeerWallpaper
The wallpaper » of a given peer has changed.

```
updatePeerWallpaper#ae3f101d flags:# wallpaper_overridden:flags.1?true peer:Peer wallpaper:flags.0?WallPaper = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| wallpaper_overridden | flags.1?true | Whether the other user has chosen a custom wallpaper for us using messages.setChatWallPaper and the for_both flag, see here » for more info. |
| peer | Peer | The peer where the wallpaper has changed. |
| wallpaper | flags.0?WallPaper | The new wallpaper, if none the wallpaper was removed and the default wallpaper should be used. |


## Type
Update

## Related pages
