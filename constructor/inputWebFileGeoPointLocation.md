# inputWebFileGeoPointLocation
Used to download a server-generated image with the map preview from a geoPoint, see the webfile docs for more info ».

```
inputWebFileGeoPointLocation#9f2221c9 geo_point:InputGeoPoint access_hash:long w:int h:int zoom:int scale:int = InputWebFileLocation;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| geo_point | InputGeoPoint | Generated from the lat, long and accuracy_radius parameters of the geoPoint |
| access_hash | long | Access hash of the geoPoint |
| w | int | Map width in pixels before applying scale; 16-1024 |
| h | int | Map height in pixels before applying scale; 16-1024 |
| zoom | int | Map zoom level; 13-20 |
| scale | int | Map scale; 1-3 |


## Type
InputWebFileLocation

## Related pages
