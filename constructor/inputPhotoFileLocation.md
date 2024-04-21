# inputPhotoFileLocation
Use this object to download a photo with upload.getFile method

```
inputPhotoFileLocation#40181ffe id:long access_hash:long file_reference:bytes thumb_size:string = InputFileLocation;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | Photo ID, obtained from the photo object |
| access_hash | long | Photo's access hash, obtained from the photo object |
| file_reference | bytes | File reference |
| thumb_size | string | The PhotoSize to download: must be set to the type field of the desired PhotoSize object of the photo |


## Type
InputFileLocation

## Related pages
