# photo
Photo

```
photo#fb197a65 flags:# has_stickers:flags.0?true id:long access_hash:long file_reference:bytes date:int sizes:Vector<PhotoSize> video_sizes:flags.1?Vector<VideoSize> dc_id:int = Photo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_stickers | flags.0?true | Whether the photo has mask stickers attached to it |
| id | long | ID |
| access_hash | long | Access hash |
| file_reference | bytes | file reference |
| date | int | Date of upload |
| sizes | Vector<PhotoSize> | Available sizes for download |
| video_sizes | flags.1?Vector<VideoSize> | For animated profiles, the MPEG4 videos |
| dc_id | int | DC ID to use for download |


## Type
Photo

## Related pages
