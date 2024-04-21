# mediaAreaVenue
Represents a location tag attached to a story, with additional venue information.

```
mediaAreaVenue#be82db9c coordinates:MediaAreaCoordinates geo:GeoPoint title:string address:string provider:string venue_id:string venue_type:string = MediaArea;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| coordinates | MediaAreaCoordinates | The size and location of the media area corresponding to the location sticker on top of the story media. |
| geo | GeoPoint | Coordinates of the venue |
| title | string | Venue name |
| address | string | Address |
| provider | string | Venue provider: currently only "foursquare" needs to be supported. |
| venue_id | string | Venue ID in the provider's database |
| venue_type | string | Venue type in the provider's database |


## Type
MediaArea

## Related pages
