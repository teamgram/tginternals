# upload.reuploadCdnFile
Request a reupload of a certain file to a CDN DC.

```
---functions---
upload.reuploadCdnFile#9b2754a8 file_token:bytes request_token:bytes = Vector<FileHash>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| file_token | bytes | File token |
| request_token | bytes | Request token |


## Result
Vector<FileHash>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CDN_METHOD_INVALID | You can't call this method in a CDN DC. |
| 500 | CDN_UPLOAD_TIMEOUT | A server-side timeout occurred while reuploading the file to the CDN DC. |
| 400 | FILE_TOKEN_INVALID | The specified file token is invalid. |
| 400 | RSA_DECRYPT_FAILED | Internal RSA decryption failed. |

