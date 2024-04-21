# upload.getFileHashes
Get SHA256 hashes for verifying downloaded files

```
---functions---
upload.getFileHashes#9156982a location:InputFileLocation offset:long = Vector<FileHash>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| location | InputFileLocation | File |
| offset | long | Offset from which to get file hashes |


## Result
Vector<FileHash>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LOCATION_INVALID | The provided location is invalid. |

