# upload.getWebfile
Returns content of a web file, by proxying the request through telegram, see the webfile docs for more info.

```
upload.webFile#21e753bc size:int mime_type:string file_type:storage.FileType mtime:int bytes:bytes = upload.WebFile;
---functions---
upload.getWebFile#24e6818d location:InputWebFileLocation offset:int limit:int = upload.WebFile;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| location | InputWebFileLocation | The file to download |
| offset | int | Number of bytes to be skipped |
| limit | int | Number of bytes to be returned |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |
| 400 | LOCATION_INVALID | The provided location is invalid. |

