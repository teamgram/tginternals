# inputBotInlineMessageMediaGeo
Geolocation

```
inputBotInlineMessageMediaGeo#96929a85 flags:# geo_point:InputGeoPoint heading:flags.0?int period:flags.1?int proximity_notification_radius:flags.3?int reply_markup:flags.2?ReplyMarkup = InputBotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| geo_point | InputGeoPoint | Geolocation |
| heading | flags.0?int | For live locations, a direction in which the location moves, in degrees; 1-360 |
| period | flags.1?int | Validity period |
| proximity_notification_radius | flags.3?int | For live locations, a maximum distance to another chat member for proximity alerts, in meters (0-100000) |
| reply_markup | flags.2?ReplyMarkup | Reply markup for bot/inline keyboards |


## Type
InputBotInlineMessage

## Related pages
