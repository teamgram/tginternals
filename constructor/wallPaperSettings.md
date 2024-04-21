# wallPaperSettings
Wallpaper rendering information.

```
wallPaperSettings#372efcd0 flags:# blur:flags.1?true motion:flags.2?true background_color:flags.0?int second_background_color:flags.4?int third_background_color:flags.5?int fourth_background_color:flags.6?int intensity:flags.3?int rotation:flags.4?int emoticon:flags.7?string = WallPaperSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| blur | flags.1?true | For image wallpapers »: if set, the JPEG must be downscaled to fit in 450x450 square and then box-blurred with radius 12. |
| motion | flags.2?true | If set, the background needs to be slightly moved when the device is rotated. |
| background_color | flags.0?int | Used for solid », gradient » and freeform gradient » fills. |
| second_background_color | flags.4?int | Used for gradient » and freeform gradient » fills. |
| third_background_color | flags.5?int | Used for freeform gradient » fills. |
| fourth_background_color | flags.6?int | Used for freeform gradient » fills. |
| intensity | flags.3?int | Used for pattern wallpapers ». |
| rotation | flags.4?int | Clockwise rotation angle of the gradient, in degrees; 0-359. Should be always divisible by 45. |
| emoticon | flags.7?string | If set, this wallpaper can be used as a channel wallpaper and is represented by the specified UTF-8 emoji. |


## Type
WallPaperSettings

## Related pages
