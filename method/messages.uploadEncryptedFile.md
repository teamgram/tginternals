# messages.uploadEncryptedFile
Upload encrypted file and associate it to a secret chat

```
encryptedFileEmpty#c21f497e = EncryptedFile;
encryptedFile#a8008cd8 id:long access_hash:long size:long dc_id:int key_fingerprint:int = EncryptedFile;
---functions---
messages.uploadEncryptedFile#5057c497 peer:InputEncryptedChat file:InputEncryptedFile = EncryptedFile;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputEncryptedChat | The secret chat to associate the file to |
| file | InputEncryptedFile | The file |


## Result
EncryptedFile

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

