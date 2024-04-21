# reactionCount
Reactions

```
reactionCount#a3d1cb80 flags:# chosen_order:flags.0?int reaction:Reaction count:int = ReactionCount;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| chosen_order | flags.0?int | If set, indicates that the current user also sent this reaction. The integer value indicates when was the reaction added: the bigger the value, the newer the reaction. |
| reaction | Reaction | The reaction. |
| count | int | Number of users that reacted with this emoji. |


## Type
ReactionCount

## Related pages
