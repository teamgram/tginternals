# upload.getCdnFileHashes
Get SHA256 hashes for verifying downloaded CDN files

```
---functions---
upload.getCdnFileHashes#91dc3f31 file_token:bytes offset:long = Vector<FileHash>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| file_token | bytes | File |
| offset | long | Offset from which to start getting hashes |


## Result
Vector<FileHash>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CDN_METHOD_INVALID | You can't call this method in a CDN DC. |
| 400 | FILE_TOKEN_INVALID | The specified file token is invalid. |
| 400 | RSA_DECRYPT_FAILED | Internal RSA decryption failed. |

