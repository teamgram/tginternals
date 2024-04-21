# document
Document

```
document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| id | long | Document ID |
| access_hash | long | Check sum, dependent on document ID |
| file_reference | bytes | File reference |
| date | int | Creation date |
| mime_type | string | MIME type |
| size | long | Size |
| thumbs | flags.0?Vector<PhotoSize> | Thumbnails |
| video_thumbs | flags.1?Vector<VideoSize> | Video thumbnails |
| dc_id | int | DC ID |
| attributes | Vector<DocumentAttribute> | Attributes |


## Type
Document

## Related pages
