# stories.storyReactionsList
List of peers that reacted to or intercated with a specific story

```
stories.storyReactionsList#aa5f789c flags:# count:int reactions:Vector<StoryReaction> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryReactionsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of reactions matching query |
| reactions | Vector<StoryReaction> | List of peers that reacted to or interacted with a specific story |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |
| next_offset | flags.0?string | If set, indicates the next offset to use to load more results by invoking stories.getStoryReactionsList. |


## Type
stories.StoryReactionsList

## Related pages
