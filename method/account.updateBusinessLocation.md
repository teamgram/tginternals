# account.updateBusinessLocation
Businesses » may advertise their location using this method, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.updateBusinessLocation#9e6b131a flags:# geo_point:flags.1?InputGeoPoint address:flags.0?string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| geo_point | flags.1?InputGeoPoint | Optional, contains a set of geographical coordinates. |
| address | flags.0?string | Mandatory when setting/updating the location, contains a textual description of the address (max 96 UTF-8 chars). |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

