# channels.reorderUsernames
Reorder active usernames

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.reorderUsernames#b45ced1d channel:InputChannel order:Vector<string> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | The supergroup or channel |
| order | Vector<string> | The new order for active usernames. All active usernames must be specified. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHAT_NOT_MODIFIED | No changes were made to chat information because the new information you passed is identical to the current information. |

