# stories.allStories
Full list of active (or active and hidden) stories.

```
stories.allStories#6efc5e81 flags:# has_more:flags.0?true count:int state:string peer_stories:Vector<PeerStories> chats:Vector<Chat> users:Vector<User> stealth_mode:StoriesStealthMode = stories.AllStories;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_more | flags.0?true | Whether more results can be fetched as described here ». |
| count | int | Total number of active (or active and hidden) stories |
| state | string | State to use for pagination |
| peer_stories | Vector<PeerStories> | Stories |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |
| stealth_mode | StoriesStealthMode | Current stealth mode information |


## Type
stories.AllStories

## Related pages
