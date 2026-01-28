# smsjobs.finishJob
Finish an SMS job (official clients only).

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
smsjobs.finishJob#4f1ebf24 flags:# job_id:string error:flags.0?string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| job_id | string | Job ID. |
| error | flags.0?string | If failed, the error. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SMSJOB_ID_INVALID | The specified job ID is invalid. |

