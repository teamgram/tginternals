# account.uploadRingtone
Upload notification sound, use account.saveRingtone to convert it and add it to the list of saved notification sounds.

```
documentEmpty#36f8c871 id:long = Document;
document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;
---functions---
account.uploadRingtone#831a83a2 file:InputFile file_name:string mime_type:string = Document;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| file | InputFile | Notification sound |
| file_name | string | File name |
| mime_type | string | MIME type of file |


## Result
Document

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

