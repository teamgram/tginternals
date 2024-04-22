# InputFile
Defines a file uploaded by the client.

```
inputFile#f52ff27f id:long parts:int name:string md5_checksum:string = InputFile;
inputFileBig#fa4f0bb5 id:long parts:int name:string = InputFile;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputFile | Defines a file saved in parts using the method upload.saveFilePart. |
| inputFileBig | Assigns a big file (over 10 MB in size), saved in part using the method upload.saveBigFilePart. |


## Methods
| Method | Description |
| ---- | ----------- |


