# payments.suggestedStarRefBots
A list of suggested mini apps with available affiliate programs

```
payments.suggestedStarRefBots#b4d5d859 flags:# count:int suggested_bots:Vector<StarRefProgram> users:Vector<User> next_offset:flags.0?string = payments.SuggestedStarRefBots;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of results (for pagination) |
| suggested_bots | Vector<StarRefProgram> | Suggested affiliate programs (full or partial list to be fetched using pagination) |
| users | Vector<User> | Peers mentioned in suggested_bots |
| next_offset | flags.0?string | Next offset for pagination |


## Type
payments.SuggestedStarRefBots

## Related pages
