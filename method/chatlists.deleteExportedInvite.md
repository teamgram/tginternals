# chatlists.deleteExportedInvite
Delete a previously created chat folder deep link ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
chatlists.deleteExportedInvite#719c5c5e chatlist:InputChatlist slug:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chatlist | InputChatlist | The related folder |
| slug | string | slug obtained from the chat folder deep link ». |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILTER_ID_INVALID | The specified filter ID is invalid. |
| 400 | FILTER_NOT_SUPPORTED | The specified filter cannot be used in this context. |

