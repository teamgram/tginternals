# smsjobs.getSmsJob
Get info about an SMS job (official clients only).

```
smsJob#e6a1eeb8 job_id:string phone_number:string text:string = SmsJob;
---functions---
smsjobs.getSmsJob#778d902f job_id:string = SmsJob;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| job_id | string | Job ID |


## Result
SmsJob

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SMSJOB_ID_INVALID | The specified job ID is invalid. |

