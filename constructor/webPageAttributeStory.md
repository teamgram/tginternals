# webPageAttributeStory
Webpage preview of a Telegram story

```
webPageAttributeStory#2e94c3e7 flags:# peer:Peer id:int story:flags.0?StoryItem = WebPageAttribute;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | Peer | Peer that posted the story |
| id | int | Story ID |
| story | flags.0?StoryItem | May contain the story, if not the story should be fetched when and if needed using stories.getStoriesByID with the above id and peer. |


## Type
WebPageAttribute

## Related pages
