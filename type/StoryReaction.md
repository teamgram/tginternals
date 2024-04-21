# StoryReaction
How a certain peer reacted to or interacted with a story

```
storyReaction#6090d6d5 peer_id:Peer date:int reaction:Reaction = StoryReaction;
storyReactionPublicForward#bbab2643 message:Message = StoryReaction;
storyReactionPublicRepost#cfcd0f13 peer_id:Peer story:StoryItem = StoryReaction;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| storyReaction | How a certain peer reacted to a story |
| storyReactionPublicForward | A certain peer has forwarded the story as a message to a public chat or channel. |
| storyReactionPublicRepost | A certain peer has reposted the story. |


## Methods
| Method | Description |
| ---- | ----------- |


