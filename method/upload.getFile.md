# upload.getFile
Returns content of a whole file or its part.

```
upload.file#96a18d5 type:storage.FileType mtime:int bytes:bytes = upload.File;
upload.fileCdnRedirect#f18cda44 dc_id:int file_token:bytes encryption_key:bytes encryption_iv:bytes file_hashes:Vector<FileHash> = upload.File;
---functions---
upload.getFile#be5335be flags:# precise:flags.0?true cdn_supported:flags.1?true location:InputFileLocation offset:long limit:int = upload.File;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| precise | flags.0?true | Disable some checks on limit and offset values, useful for example to stream videos by keyframes |
| cdn_supported | flags.1?true | Whether the current client supports CDN downloads |
| location | InputFileLocation | File location |
| offset | long | Number of bytes to be skipped |
| limit | int | Number of bytes to be returned |


## Result
upload.File

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CDN_METHOD_INVALID | You can't call this method in a CDN DC. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 406 | FILEREF_UPGRADE_NEEDED | The client has to be updated in order to support file references. |
| 400 | FILE_ID_INVALID | The provided file id is invalid. |
| 400 | FILE_REFERENCE_* | The file reference expired, it must be refreshed. |
| 400 | FILE_REFERENCE_EXPIRED | File reference expired, it must be refetched as described in the documentation. |
| 400 | LIMIT_INVALID | The provided limit is invalid. |
| 400 | LOCATION_INVALID | The provided location is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | OFFSET_INVALID | The provided offset is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

