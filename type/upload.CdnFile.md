# upload.CdnFile
Represents the download status of a CDN file

```
upload.cdnFileReuploadNeeded#eea8e46e request_token:bytes = upload.CdnFile;
upload.cdnFile#a99fca4f bytes:bytes = upload.CdnFile;

---functions---

upload.getCdnFile#395f69da file_token:bytes offset:long limit:int = upload.CdnFile;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| upload.cdnFileReuploadNeeded | The file was cleared from the temporary RAM cache of the CDN and has to be re-uploaded. |
| upload.cdnFile | Represent a chunk of a CDN file. |


## Methods
| Method | Description |
| ---- | ----------- |
| upload.getCdnFile | Download a CDN file. |


