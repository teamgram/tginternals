# stickers.checkShortName
Check whether the given short name is available

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stickers.checkShortName#284b3639 short_name:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| short_name | string | Short name |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SHORT_NAME_INVALID | The specified short name is invalid. |
| 400 | SHORT_NAME_OCCUPIED | The specified short name is already in use. |

