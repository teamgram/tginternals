# inputEncryptedFileUploaded
Sets new encrypted file saved by parts using upload.saveFilePart method.

```
inputEncryptedFileUploaded#64bd0306 id:long parts:int md5_checksum:string key_fingerprint:int = InputEncryptedFile;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | Random file ID created by client |
| parts | int | Number of saved parts |
| md5_checksum | string | In case md5-HASH of the (already encrypted) file was transmitted, file content will be checked prior to use |
| key_fingerprint | int | 32-bit fingerprint of the key used to encrypt a file |


## Type
InputEncryptedFile

## Related pages
