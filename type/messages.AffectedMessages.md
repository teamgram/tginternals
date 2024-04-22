# Messages.AffectedMessages
Messages affected by changes

```
messages.affectedMessages#84d19185 pts:int pts_count:int = messages.AffectedMessages;

---functions---

messages.readHistory#e306d3a peer:InputPeer max_id:int = messages.AffectedMessages;
messages.deleteMessages#e58e95d2 flags:# revoke:flags.0?true id:Vector<int> = messages.AffectedMessages;
messages.readMessageContents#36a73f77 id:Vector<int> = messages.AffectedMessages;

channels.deleteMessages#84c1fd4e channel:InputChannel id:Vector<int> = messages.AffectedMessages;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.affectedMessages | Events affected by operation |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.readHistory | Marks message history as read. |
| messages.deleteMessages | Deletes messages by their identifiers. |
| messages.readMessageContents | Notifies the sender about the recipient having listened a voice message or watched a video. |
| channels.deleteMessages | Delete messages in a channel/supergroup |


