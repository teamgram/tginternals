# Channels.ChannelParticipants
Channel/supergroup participants

```
channels.channelParticipants#9ab0feaf count:int participants:Vector<ChannelParticipant> chats:Vector<Chat> users:Vector<User> = channels.ChannelParticipants;
channels.channelParticipantsNotModified#f0173fe9 = channels.ChannelParticipants;

---functions---

channels.getParticipants#77ced9d0 channel:InputChannel filter:ChannelParticipantsFilter offset:int limit:int hash:long = channels.ChannelParticipants;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| channels.channelParticipants | Represents multiple channel participants |
| channels.channelParticipantsNotModified | No new participant info could be found |


## Methods
| Method | Description |
| ---- | ----------- |
| channels.getParticipants | Get the participants of a supergroup/channel |


