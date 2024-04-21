# messages.affectedHistory
Affected part of communication history with the user or in a chat.

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| pts | int | Number of events occurred in a text box |
| pts_count | int | Number of affected events |
| offset | int | If a parameter contains positive value, it is necessary to repeat the method call using the given value; during the proceeding of all the history the value itself shall gradually decrease |


## Type
messages.AffectedHistory

## Related pages
