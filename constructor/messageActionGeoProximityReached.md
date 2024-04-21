# messageActionGeoProximityReached
A user of the chat is now in proximity of another user

```
messageActionGeoProximityReached#98e0d697 from_id:Peer to_id:Peer distance:int = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| from_id | Peer | The user or chat that is now in proximity of to_id |
| to_id | Peer | The user or chat that subscribed to live geolocation proximity alerts |
| distance | int | Distance, in meters (0-100000) |


## Type
MessageAction

## Related pages
