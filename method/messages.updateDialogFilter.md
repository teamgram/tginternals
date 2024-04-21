# messages.updateDialogFilter
Update folder

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.updateDialogFilter#1ad4a04a flags:# id:int filter:flags.0?DialogFilter = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| id | int | Folder ID |
| filter | flags.0?DialogFilter | Folder info |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHATLIST_EXCLUDE_INVALID | The specified exclude_peers are invalid. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | FILTER_ID_INVALID | The specified filter ID is invalid. |
| 400 | FILTER_INCLUDE_EMPTY | The include_peers vector of the filter is empty. |
| 400 | FILTER_TITLE_EMPTY | The title field of the filter is empty. |

