# payments.clearSavedInfo
Clear saved payment information

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.clearSavedInfo#d83d70c1 flags:# credentials:flags.0?true info:flags.1?true = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| credentials | flags.0?true | Remove saved payment credentials |
| info | flags.1?true | Clear the last order settings saved by the user |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

