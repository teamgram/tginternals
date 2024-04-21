# storyViews
Aggregated view and reaction information of a story.

```
storyViews#8d595cd6 flags:# has_viewers:flags.1?true views_count:int forwards_count:flags.2?int reactions:flags.3?Vector<ReactionCount> reactions_count:flags.4?int recent_viewers:flags.0?Vector<long> = StoryViews;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_viewers | flags.1?true | If set, indicates that the viewers list is currently viewable, and was not yet deleted because the story has expired while the user didn't have a Premium account. |
| views_count | int | View counter of the story |
| forwards_count | flags.2?int | Forward counter of the story |
| reactions | flags.3?Vector<ReactionCount> | All reactions sent to this story |
| reactions_count | flags.4?int | Number of reactions added to the story |
| recent_viewers | flags.0?Vector<long> | User IDs of some recent viewers of the story |


## Type
StoryViews

## Related pages
