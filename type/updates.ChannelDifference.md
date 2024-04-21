# updates.ChannelDifference
Contains the difference (new messages) between our local channel state and the remote state

```
updates.channelDifferenceEmpty#3e11affb flags:# final:flags.0?true pts:int timeout:flags.1?int = updates.ChannelDifference;
updates.channelDifferenceTooLong#a4bcc6fe flags:# final:flags.0?true timeout:flags.1?int dialog:Dialog messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = updates.ChannelDifference;
updates.channelDifference#2064674e flags:# final:flags.0?true pts:int timeout:flags.1?int new_messages:Vector<Message> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> = updates.ChannelDifference;

---functions---

updates.getChannelDifference#3173d78 flags:# force:flags.0?true channel:InputChannel filter:ChannelMessagesFilter pts:int limit:int = updates.ChannelDifference;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| updates.channelDifferenceEmpty | There are no new updates |
| updates.channelDifferenceTooLong | The provided pts + limit < remote pts. Simply, there are too many updates to be fetched (more than limit), the client has to resolve the update gap in one of the following ways (assuming the existence of a persistent database to locally store messages):1. Delete all known messages in the chat, begin from scratch by refetching all messages manually with messages.getHistory. It is easy to implement, but suddenly disappearing messages look awful to the user.2. Save all messages loaded in the memory until application restart, but delete all messages from the database. Messages left in the memory must be lazily updated using calls to messages.getHistory.      It will look much smoother to the user, they will need to redownload messages only after client restart.      Unsynchronized messages left in memory shouldn't be saved to the database, results of messages.getHistory and messages.getMessages must be used to update the state of deleted and edited messages left in the memory.3. Save all messages loaded in the memory and stored in the database without saving that some messages form continuous ranges.      Messages in the database will be excluded when paginating through or searching the local message history after application restart and will be available only through individual message queries.      Every message should still be checked using messages.getHistory.      It has more disadvantages over 2) than advantages.4. Save all messages with saving all data about continuous message ranges.      Messages from the database may be used when paginating through or searching the local message history.      The messages should still be lazily checked using messages.getHistory, but they are still available offline.      It is the best way for gaps support, but it is pretty hard to implement correctly.It should be also noted that some messages like live location messages shouldn't be deleted. |
| updates.channelDifference | The new updates |


## Methods
| Method | Description |
| ---- | ----------- |
| updates.getChannelDifference | Returns the difference between the current state of updates of a certain channel and transmitted. |


