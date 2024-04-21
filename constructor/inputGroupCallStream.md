# inputGroupCallStream
Chunk of a livestream

```
inputGroupCallStream#598a92a flags:# call:InputGroupCall time_ms:long scale:int video_channel:flags.0?int video_quality:flags.0?int = InputFileLocation;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| call | InputGroupCall | Livestream info |
| time_ms | long | Timestamp in milliseconds |
| scale | int | Specifies the duration of the video segment to fetch in milliseconds, by bitshifting 1000 to the right scale times: duration_ms := 1000 >> scale |
| video_channel | flags.0?int | Selected video channel |
| video_quality | flags.0?int | Selected video quality (0 = lowest, 1 = medium, 2 = best) |


## Type
InputFileLocation

## Related pages
