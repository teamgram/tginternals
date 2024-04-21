# account.reorderUsernames
Reorder usernames associated with the currently logged-in user.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.reorderUsernames#ef500eab order:Vector<string> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| order | Vector<string> | The new order for active usernames. All active usernames must be specified. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ORDER_INVALID | The specified username order is invalid. |

