# upload.saveFilePart
Saves a part of file for further sending to one of the methods.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
upload.saveFilePart#b304a621 file_id:long file_part:int bytes:bytes = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| file_id | long | Random file identifier created by the client |
| file_part | int | Numerical order of a part |
| bytes | bytes | Binary data, content of a part |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILE_PART_EMPTY | The provided file part is empty. |
| 400 | FILE_PART_INVALID | The file part number is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |

