# storyItemSkipped
Represents an active story, whose full information was omitted for space and performance reasons; use stories.getStoriesByID to fetch full info about the skipped story when and if needed.

```
storyItemSkipped#ffadc913 flags:# close_friends:flags.8?true id:int date:int expire_date:int = StoryItem;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| close_friends | flags.8?true | Whether this story can only be viewed by our close friends, see here » for more info |
| id | int | Story ID |
| date | int | When was the story posted. |
| expire_date | int | When does the story expire. |


## Type
StoryItem

## Related pages
