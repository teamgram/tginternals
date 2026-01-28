# searchPostsFlood
Indicates if the specified global post search » requires payment.

```
searchPostsFlood#3e0b5b6a flags:# query_is_free:flags.0?true total_daily:int remains:int wait_till:flags.1?int stars_amount:long = SearchPostsFlood;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query_is_free | flags.0?true | The specified query is free (and it will not use up free search slots). |
| total_daily | int | Total number of daily free search slots. |
| remains | int | Remaining number of free search slots. |
| wait_till | flags.1?int | If there are no more search slots, specifies the unixtime when more search slots will be available. |
| stars_amount | long | The number of Telegram Stars to pay for each non-free search. |


## Type
SearchPostsFlood

## Related pages
