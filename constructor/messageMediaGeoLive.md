# messageMediaGeoLive
Indicates a live geolocation

```
messageMediaGeoLive#b940c666 flags:# geo:GeoPoint heading:flags.0?int period:int proximity_notification_radius:flags.1?int = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| geo | GeoPoint | Geolocation |
| heading | flags.0?int | For live locations, a direction in which the location moves, in degrees; 1-360 |
| period | int | Validity period of provided geolocation |
| proximity_notification_radius | flags.1?int | For live locations, a maximum distance to another chat member for proximity alerts, in meters (0-100000). |


## Type
MessageMedia

## Related pages
