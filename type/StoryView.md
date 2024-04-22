# StoryView
Story view date and reaction information

```
storyView#b0bdeac5 flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true user_id:long date:int reaction:flags.2?Reaction = StoryView;
storyViewPublicForward#9083670b flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true message:Message = StoryView;
storyViewPublicRepost#bd74cf49 flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true peer_id:Peer story:StoryItem = StoryView;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| storyView | Story view date and reaction information |
| storyViewPublicForward | A certain peer has forwarded the story as a message to a public chat or channel. |
| storyViewPublicRepost | A certain peer has reposted the story. |


## Methods
| Method | Description |
| ---- | ----------- |


