# stories.StoryReactionsList
List of peers that reacted to a specific story

```
stories.storyReactionsList#aa5f789c flags:# count:int reactions:Vector<StoryReaction> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryReactionsList;

---functions---

stories.getStoryReactionsList#b9b2881f flags:# forwards_first:flags.2?true peer:InputPeer id:int reaction:flags.0?Reaction offset:flags.1?string limit:int = stories.StoryReactionsList;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| stories.storyReactionsList | List of peers that reacted to or intercated with a specific story |


## Methods
| Method | Description |
| ---- | ----------- |
| stories.getStoryReactionsList | Get the reaction and interaction list of a story posted to a channel, along with the sender of each reaction.Can only be used by channel admins. |


