# FileHash
SHA256 Hash of an uploaded file, to be checked for validity after download

```
fileHash#f39b035c offset:long limit:int hash:bytes = FileHash;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| offset | long | Offset from where to start computing SHA-256 hash |
| limit | int | Length |
| hash | bytes | SHA-256 Hash of file chunk, to be checked for validity after download |


## Type
FileHash

## Related pages
