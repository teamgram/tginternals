# videoSize
An animated profile picture in MPEG4 format

```
videoSize#de33b094 flags:# type:string w:int h:int size:int video_start_ts:flags.0?double = VideoSize;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| type | string | u for animated profile pictures, and v for trimmed and downscaled video previews |
| w | int | Video width |
| h | int | Video height |
| size | int | File size |
| video_start_ts | flags.0?double | Timestamp that should be shown as static preview to the user (seconds) |


## Type
VideoSize

## Related pages
