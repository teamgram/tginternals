# botInlineMessageMediaVenue
Send a venue

```
botInlineMessageMediaVenue#8a86659c flags:# geo:GeoPoint title:string address:string provider:string venue_id:string venue_type:string reply_markup:flags.2?ReplyMarkup = BotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| geo | GeoPoint | Geolocation of venue |
| title | string | Venue name |
| address | string | Address |
| provider | string | Venue provider: currently only "foursquare" and "gplaces" (Google Places) need to be supported |
| venue_id | string | Venue ID in the provider's database |
| venue_type | string | Venue type in the provider's database |
| reply_markup | flags.2?ReplyMarkup | Inline keyboard |


## Type
BotInlineMessage

## Related pages
