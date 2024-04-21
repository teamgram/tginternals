# inputSecureFileUploaded
Uploaded secure file, for more info see the passport docs »

```
inputSecureFileUploaded#3334b0f0 id:long parts:int md5_checksum:string file_hash:bytes secret:bytes = InputSecureFile;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | Secure file ID |
| parts | int | Secure file part count |
| md5_checksum | string | MD5 hash of encrypted uploaded file, to be checked server-side |
| file_hash | bytes | File hash |
| secret | bytes | Secret |


## Type
InputSecureFile

## Related pages
