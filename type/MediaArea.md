# MediaArea
Represents a story media area »

```
mediaAreaVenue#be82db9c coordinates:MediaAreaCoordinates geo:GeoPoint title:string address:string provider:string venue_id:string venue_type:string = MediaArea;
inputMediaAreaVenue#b282217f coordinates:MediaAreaCoordinates query_id:long result_id:string = MediaArea;
mediaAreaGeoPoint#df8b3b22 coordinates:MediaAreaCoordinates geo:GeoPoint = MediaArea;
mediaAreaSuggestedReaction#14455871 flags:# dark:flags.0?true flipped:flags.1?true coordinates:MediaAreaCoordinates reaction:Reaction = MediaArea;
mediaAreaChannelPost#770416af coordinates:MediaAreaCoordinates channel_id:long msg_id:int = MediaArea;
inputMediaAreaChannelPost#2271f2bf coordinates:MediaAreaCoordinates channel:InputChannel msg_id:int = MediaArea;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| mediaAreaVenue | Represents a location tag attached to a story, with additional venue information. |
| inputMediaAreaVenue | Represents a location tag attached to a story, with additional venue information. |
| mediaAreaGeoPoint | Represents a geolocation tag attached to a story. |
| mediaAreaSuggestedReaction | Represents a reaction bubble. |
| mediaAreaChannelPost | Represents a channel post. |
| inputMediaAreaChannelPost | Represents a channel post |


## Methods
| Method | Description |
| ---- | ----------- |


