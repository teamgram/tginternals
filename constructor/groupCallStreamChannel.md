# groupCallStreamChannel
Info about an RTMP stream in a group call or livestream

```
groupCallStreamChannel#80eb48af channel:int scale:int last_timestamp_ms:long = GroupCallStreamChannel;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | int | Channel ID |
| scale | int | Specifies the duration of the video segment to fetch in milliseconds, by bitshifting 1000 to the right scale times: duration_ms := 1000 >> scale. |
| last_timestamp_ms | long | Last seen timestamp to easily start fetching livestream chunks using inputGroupCallStream |


## Type
GroupCallStreamChannel

## Related pages
