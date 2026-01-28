# channels.checkSearchPostsFlood
Check if the specified global post search » requires payment.

```
searchPostsFlood#3e0b5b6a flags:# query_is_free:flags.0?true total_daily:int remains:int wait_till:flags.1?int stars_amount:long = SearchPostsFlood;
---functions---
channels.checkSearchPostsFlood#22567115 flags:# query:flags.0?string = SearchPostsFlood;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query | flags.0?string | The query. |


## Result
SearchPostsFlood

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

