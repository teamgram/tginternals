# account.updateBirthday
Update our birthday, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.updateBirthday#cc6e0c11 flags:# birthday:flags.0?Birthday = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| birthday | flags.0?Birthday | Birthday. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BIRTHDAY_INVALID | An invalid age was specified, must be between 0 and 150 years. |

