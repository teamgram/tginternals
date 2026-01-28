# stories.searchPosts
Globally search for stories using a hashtag or a location media area, see here » for more info on the full flow.

```
stories.foundStories#e2de7737 flags:# count:int stories:Vector<FoundStory> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stories.FoundStories;
---functions---
stories.searchPosts#d1810907 flags:# hashtag:flags.0?string area:flags.1?MediaArea peer:flags.2?InputPeer offset:string limit:int = stories.FoundStories;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| hashtag | flags.0?string | Hashtag (without the #) |
| area | flags.1?MediaArea | A mediaAreaGeoPoint or a mediaAreaVenue.  Note mediaAreaGeoPoint areas may be searched only if they have an associated address. |
| peer | flags.2?InputPeer | If set, returns only stories posted by this peer. |
| offset | string | Offset for pagination: initially an empty string, then the next_offset from the previously returned stories.foundStories. |
| limit | int | Maximum number of results to return, see pagination |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | HASHTAG_INVALID | The specified hashtag is invalid. |

