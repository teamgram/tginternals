# inputMediaVenue
Can be used to send a venue geolocation.

```
inputMediaVenue#c13d1c11 geo_point:InputGeoPoint title:string address:string provider:string venue_id:string venue_type:string = InputMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| geo_point | InputGeoPoint | Geolocation |
| title | string | Venue name |
| address | string | Physical address of the venue |
| provider | string | Venue provider: currently only "foursquare" and "gplaces" (Google Places) need to be supported |
| venue_id | string | Venue ID in the provider's database |
| venue_type | string | Venue type in the provider's database |


## Type
InputMedia

## Related pages
