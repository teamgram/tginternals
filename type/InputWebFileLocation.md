# InputWebFileLocation
Location of remote file

```
inputWebFileLocation#c239d686 url:string access_hash:long = InputWebFileLocation;
inputWebFileGeoPointLocation#9f2221c9 geo_point:InputGeoPoint access_hash:long w:int h:int zoom:int scale:int = InputWebFileLocation;
inputWebFileAudioAlbumThumbLocation#f46fe924 flags:# small:flags.2?true document:flags.0?InputDocument title:flags.1?string performer:flags.1?string = InputWebFileLocation;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputWebFileLocation | Location of a remote HTTP(s) file |
| inputWebFileGeoPointLocation | Used to download a server-generated image with the map preview from a geoPoint, see the webfile docs for more info ». |
| inputWebFileAudioAlbumThumbLocation | Used to download an album cover for any music file using upload.getWebFile, see the webfile docs for more info ». |


## Methods
| Method | Description |
| ---- | ----------- |


