# upload.saveBigFilePart
Saves a part of a large file (over 10 MB in size) to be later passed to one of the methods.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
upload.saveBigFilePart#de7b673d file_id:long file_part:int file_total_parts:int bytes:bytes = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| file_id | long | Random file id, created by the client |
| file_part | int | Part sequence number |
| file_total_parts | int | Total number of parts |
| bytes | bytes | Binary data, part contents |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILE_PARTS_INVALID | The number of file parts is invalid. |
| 400 | FILE_PART_EMPTY | The provided file part is empty. |
| 400 | FILE_PART_INVALID | The file part number is invalid. |
| 400 | FILE_PART_SIZE_CHANGED | Provided file part size has changed. |
| 400 | FILE_PART_SIZE_INVALID | The provided file part size is invalid. |
| 400 | FILE_PART_TOO_BIG | The uploaded file part is too big. |

