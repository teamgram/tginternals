# channels.editLocation
Edit location of geogroup, see here » for more info on geogroups.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.editLocation#58e63f6d channel:InputChannel geo_point:InputGeoPoint address:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Geogroup |
| geo_point | InputGeoPoint | New geolocation |
| address | string | Address string |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_NOT_MODIFIED | No changes were made to chat information because the new information you passed is identical to the current information. |
| 400 | MEGAGROUP_GEO_REQUIRED | This method can only be invoked on a geogroup. |
| 400 | MEGAGROUP_REQUIRED | You can only use this method on a supergroup. |

