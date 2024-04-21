# inputFile
Defines a file saved in parts using the method upload.saveFilePart.

```
inputFile#f52ff27f id:long parts:int name:string md5_checksum:string = InputFile;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | Random file identifier created by the client |
| parts | int | Number of parts saved |
| name | string | Full name of the file |
| md5_checksum | string | In case the file's md5-hash was passed, contents of the file will be checked prior to use |


## Type
InputFile

## Related pages
