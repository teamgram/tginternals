# inputEncryptedFileBigUploaded
Assigns a new big encrypted file (over 10 MB in size), saved in parts using the method upload.saveBigFilePart.

```
inputEncryptedFileBigUploaded#2dc173c8 id:long parts:int key_fingerprint:int = InputEncryptedFile;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | Random file id, created by the client |
| parts | int | Number of saved parts |
| key_fingerprint | int | 32-bit imprint of the key used to encrypt the file |


## Type
InputEncryptedFile

## Related pages
