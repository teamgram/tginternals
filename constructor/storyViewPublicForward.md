# storyViewPublicForward
A certain peer has forwarded the story as a message to a public chat or channel.

```
storyViewPublicForward#9083670b flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true message:Message = StoryView;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| blocked | flags.0?true | Whether we have completely blocked this user, including from viewing more of our stories. |
| blocked_my_stories_from | flags.1?true | Whether we have blocked this user from viewing more of our stories. |
| message | Message | The message with the forwarded story. |


## Type
StoryView

## Related pages
