# messages.getDocumentByHash
Get a document by its SHA256 hash, mainly used for gifs

```
documentEmpty#36f8c871 id:long = Document;
document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;
---functions---
messages.getDocumentByHash#b1f2061f sha256:bytes size:long mime_type:string = Document;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| sha256 | bytes | SHA256 of file |
| size | long | Size of the file in bytes |
| mime_type | string | Mime type |


## Result
Document

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SHA256_HASH_INVALID | The provided SHA256 hash is invalid. |

