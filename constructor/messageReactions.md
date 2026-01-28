# messageReactions
Message reactions »

```
messageReactions#a339f0b flags:# min:flags.0?true can_see_list:flags.2?true reactions_as_tags:flags.3?true results:Vector<ReactionCount> recent_reactions:flags.1?Vector<MessagePeerReaction> top_reactors:flags.4?Vector<MessageReactor> = MessageReactions;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| min | flags.0?true | Similar to min objects, used for message reaction » constructors that are the same for all users so they don't have the reactions sent by the current user (you can use messages.getMessagesReactions to get the full reaction info). |
| can_see_list | flags.2?true | Whether messages.getMessageReactionsList can be used to see how each specific peer reacted to the message |
| reactions_as_tags | flags.3?true | If set or if there are no reactions, all present and future reactions should be treated as message tags, see here » for more info. |
| results | Vector<ReactionCount> | Reactions |
| recent_reactions | flags.1?Vector<MessagePeerReaction> | List of recent peers and their reactions |
| top_reactors | flags.4?Vector<MessageReactor> | Paid Telegram Star reactions leaderboard » for this message. |


## Type
MessageReactions

## Related pages
