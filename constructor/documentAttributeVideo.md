# documentAttributeVideo
Defines a video

```
documentAttributeVideo#d38ff1c2 flags:# round_message:flags.0?true supports_streaming:flags.1?true nosound:flags.3?true duration:double w:int h:int preload_prefix_size:flags.2?int = DocumentAttribute;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| round_message | flags.0?true | Whether this is a round video |
| supports_streaming | flags.1?true | Whether the video supports streaming |
| nosound | flags.3?true | Whether the specified document is a video file with no audio tracks (a GIF animation (even as MPEG4), for example) |
| duration | double | Duration in seconds |
| w | int | Video width |
| h | int | Video height |
| preload_prefix_size | flags.2?int | Number of bytes to preload when preloading videos (particularly video stories). |


## Type
DocumentAttribute

## Related pages
