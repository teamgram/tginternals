# bots.reorderUsernames
Reorder usernames associated to a bot we own.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.reorderUsernames#9709b1c2 bot:InputUser order:Vector<string> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The bot |
| order | Vector<string> | The new order for active usernames. All active usernames must be specified. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

