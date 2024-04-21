# messageReactions
Message reactions »

```
messageReactions#4f2b9479 flags:# min:flags.0?true can_see_list:flags.2?true results:Vector<ReactionCount> recent_reactions:flags.1?Vector<MessagePeerReaction> = MessageReactions;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| min | flags.0?true | Similar to min objects, used for message reaction » constructors that are the same for all users so they don't have the reactions sent by the current user (you can use messages.getMessagesReactions to get the full reaction info). |
| can_see_list | flags.2?true | Whether messages.getMessageReactionsList can be used to see how each specific peer reacted to the message |
| results | Vector<ReactionCount> | Reactions |
| recent_reactions | flags.1?Vector<MessagePeerReaction> | List of recent peers and their reactions |


## Type
MessageReactions

## Related pages
