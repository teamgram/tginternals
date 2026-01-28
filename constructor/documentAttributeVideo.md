# documentAttributeVideo
Defines a video

```
documentAttributeVideo#43c57c48 flags:# round_message:flags.0?true supports_streaming:flags.1?true nosound:flags.3?true duration:double w:int h:int preload_prefix_size:flags.2?int video_start_ts:flags.4?double video_codec:flags.5?string = DocumentAttribute;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| round_message | flags.0?true | Whether this is a round video |
| supports_streaming | flags.1?true | Whether the video supports streaming |
| nosound | flags.3?true | Whether the specified document is a video file with no audio tracks |
| duration | double | Duration in seconds |
| w | int | Video width |
| h | int | Video height |
| preload_prefix_size | flags.2?int | Number of bytes to preload when preloading videos (particularly video stories). |
| video_start_ts | flags.4?double | Floating point UNIX timestamp in seconds, indicating the frame of the video that should be used as static preview and thumbnail. |
| video_codec | flags.5?string | Codec used for the video, i.e. "h264", "h265", or "av1" |


## Type
DocumentAttribute

## Related pages
