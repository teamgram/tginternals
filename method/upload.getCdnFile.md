# upload.getCdnFile
Download a CDN file.

```
upload.cdnFileReuploadNeeded#eea8e46e request_token:bytes = upload.CdnFile;
upload.cdnFile#a99fca4f bytes:bytes = upload.CdnFile;
---functions---
upload.getCdnFile#395f69da file_token:bytes offset:long limit:int = upload.CdnFile;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| file_token | bytes | File token |
| offset | long | Offset of chunk to download |
| limit | int | Length of chunk to download |


## Result
upload.CdnFile

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

