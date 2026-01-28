# smsjobs.updateSettings
Update SMS job settings (official clients only).

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
smsjobs.updateSettings#93fa0bf flags:# allow_international:flags.0?true = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| allow_international | flags.0?true | Allow international numbers? |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | NOT_JOINED | The current user hasn't joined the Peer-to-Peer Login Program. |

