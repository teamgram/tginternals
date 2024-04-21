# account.setContentSettings
Set sensitive content settings (for viewing or hiding NSFW content)

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.setContentSettings#b574b16b flags:# sensitive_enabled:flags.0?true = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| sensitive_enabled | flags.0?true | Enable NSFW content |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | SENSITIVE_CHANGE_FORBIDDEN | You can't change your sensitive content settings. |

