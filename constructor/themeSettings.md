# themeSettings
Theme settings

```
themeSettings#fa58b6d4 flags:# message_colors_animated:flags.2?true base_theme:BaseTheme accent_color:int outbox_accent_color:flags.3?int message_colors:flags.0?Vector<int> wallpaper:flags.1?WallPaper = ThemeSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| message_colors_animated | flags.2?true | If set, the freeform gradient fill needs to be animated on every sent message. |
| base_theme | BaseTheme | Base theme |
| accent_color | int | Accent color, ARGB format |
| outbox_accent_color | flags.3?int | Accent color of outgoing messages in ARGB format |
| message_colors | flags.0?Vector<int> | The fill to be used as a background for outgoing messages, in RGB24 format. If just one or two equal colors are provided, describes a solid fill of a background. If two different colors are provided, describes the top and bottom colors of a 0-degree gradient.If three or four colors are provided, describes a freeform gradient fill of a background. |
| wallpaper | flags.1?WallPaper | Wallpaper |


## Type
ThemeSettings

## Related pages
