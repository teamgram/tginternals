# upload.fileCdnRedirect
The file must be downloaded from a CDN DC.

```
upload.fileCdnRedirect#f18cda44 dc_id:int file_token:bytes encryption_key:bytes encryption_iv:bytes file_hashes:Vector<FileHash> = upload.File;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| dc_id | int | CDN DC ID |
| file_token | bytes | File token (see CDN files) |
| encryption_key | bytes | Encryption key (see CDN files) |
| encryption_iv | bytes | Encryption IV (see CDN files) |
| file_hashes | Vector<FileHash> | File hashes (see CDN files) |


## Type
upload.File

## Related pages
