# storyViewPublicRepost
A certain peer has reposted the story.

```
storyViewPublicRepost#bd74cf49 flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true peer_id:Peer story:StoryItem = StoryView;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| blocked | flags.0?true | Whether we have completely blocked this user, including from viewing more of our stories. |
| blocked_my_stories_from | flags.1?true | Whether we have blocked this user from viewing more of our stories. |
| peer_id | Peer | The peer that reposted the story. |
| story | StoryItem | The reposted story. |


## Type
StoryView

## Related pages
