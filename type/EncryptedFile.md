# EncryptedFile
Seta an encrypted file.

```
encryptedFileEmpty#c21f497e = EncryptedFile;
encryptedFile#a8008cd8 id:long access_hash:long size:long dc_id:int key_fingerprint:int = EncryptedFile;

---functions---

messages.uploadEncryptedFile#5057c497 peer:InputEncryptedChat file:InputEncryptedFile = EncryptedFile;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| encryptedFileEmpty | Empty constructor, non-existing file. |
| encryptedFile | Encrypted file. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.uploadEncryptedFile | Upload encrypted file and associate it to a secret chat |


