# stories.storyViewsList
Reaction and view counters for a story

```
stories.storyViewsList#59d78fc5 flags:# count:int views_count:int forwards_count:int reactions_count:int views:Vector<StoryView> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryViewsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of results that can be fetched |
| views_count | int | Total number of story views |
| forwards_count | int | Total number of story forwards/reposts |
| reactions_count | int | Number of reactions that were added to the story |
| views | Vector<StoryView> | Story view date and reaction information |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |
| next_offset | flags.0?string | Offset for pagination |


## Type
stories.StoryViewsList

## Related pages
