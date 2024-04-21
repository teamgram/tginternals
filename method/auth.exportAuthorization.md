# auth.exportAuthorization
Returns data for copying authorization to another data-center.

```
auth.exportedAuthorization#b434e2b8 id:long bytes:bytes = auth.ExportedAuthorization;
---functions---
auth.exportAuthorization#e5bfffcd dc_id:int = auth.ExportedAuthorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| dc_id | int | Number of a target data-center |


## Result
auth.ExportedAuthorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DC_ID_INVALID | The provided DC ID is invalid. |

