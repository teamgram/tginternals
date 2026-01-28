# bots.getPopularAppBots
Fetch popular Main Mini Apps, to be used in the apps tab of global search ».

```
bots.popularAppBots#1991b13b flags:# next_offset:flags.0?string users:Vector<User> = bots.PopularAppBots;
---functions---
bots.getPopularAppBots#c2510192 offset:string limit:int = bots.PopularAppBots;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| offset | string | Offset for pagination, initially an empty string, then re-use the next_offset returned by the previous query. |
| limit | int | Maximum number of results to return, see pagination |


## Result
bots.PopularAppBots

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

