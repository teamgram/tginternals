# storyView
Story view date and reaction information

```
storyView#b0bdeac5 flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true user_id:long date:int reaction:flags.2?Reaction = StoryView;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| blocked | flags.0?true | Whether we have completely blocked this user, including from viewing more of our stories. |
| blocked_my_stories_from | flags.1?true | Whether we have blocked this user from viewing more of our stories. |
| user_id | long | The user that viewed the story |
| date | int | When did the user view the story |
| reaction | flags.2?Reaction | If present, contains the reaction that the user left on the story |


## Type
StoryView

## Related pages
