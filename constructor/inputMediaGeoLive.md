# inputMediaGeoLive
Live geolocation

```
inputMediaGeoLive#971fa843 flags:# stopped:flags.0?true geo_point:InputGeoPoint heading:flags.2?int period:flags.1?int proximity_notification_radius:flags.3?int = InputMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| stopped | flags.0?true | Whether sending of the geolocation was stopped |
| geo_point | InputGeoPoint | Current geolocation |
| heading | flags.2?int | For live locations, a direction in which the location moves, in degrees; 1-360. |
| period | flags.1?int | Validity period of the current location |
| proximity_notification_radius | flags.3?int | For live locations, a maximum distance to another chat member for proximity alerts, in meters (0-100000) |


## Type
InputMedia

## Related pages
