# stories.foundStories
Stories found using global story search ».

```
stories.foundStories#e2de7737 flags:# count:int stories:Vector<FoundStory> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stories.FoundStories;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of results found for the query. |
| stories | Vector<FoundStory> | Matching stories. |
| next_offset | flags.0?string | Offset used to fetch the next page, if not set this is the final page. |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |


## Type
stories.FoundStories

## Related pages
