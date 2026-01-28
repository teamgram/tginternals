# initConnection
Initialize connection

```
---functions---
initConnection#c1cd5ea9 {X:Type} flags:# api_id:int device_model:string system_version:string app_version:string system_lang_code:string lang_pack:string lang_code:string proxy:flags.0?InputClientProxy params:flags.1?JSONValue query:!X = X;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| api_id | int | Application identifier (see. App configuration) |
| device_model | string | Device model |
| system_version | string | Operation system version |
| app_version | string | Application version |
| system_lang_code | string | Code for the language used on the device's OS, ISO 639-1 standard |
| lang_pack | string | Platform identifier (i.e. android, tdesktop, etc). |
| lang_code | string | Either an ISO 639-1 language code or a language pack name obtained from a language pack link. |
| proxy | flags.0?InputClientProxy | Info about an MTProto proxy |
| params | flags.1?JSONValue | Additional initConnection parameters. For now, only the tz_offset field is supported, for specifying the timezone offset in seconds. |
| query | !X | The query itself |


## Result
Returns the type returned by the invoked method.

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CONNECTION_LAYER_INVALID | Layer invalid. |

