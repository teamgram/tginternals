# account.saveAutoDownloadSettings
Change media autodownload settings

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.saveAutoDownloadSettings#76f36233 flags:# low:flags.0?true high:flags.1?true settings:AutoDownloadSettings = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| low | flags.0?true | Whether to save media in the low data usage preset |
| high | flags.1?true | Whether to save media in the high data usage preset |
| settings | AutoDownloadSettings | Media autodownload settings |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

