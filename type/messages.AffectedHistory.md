# messages.AffectedHistory
Object contains info on affected part of communication history with the user or in a chat.

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;

---functions---

messages.deleteHistory#b08f922a flags:# just_clear:flags.0?true revoke:flags.1?true peer:InputPeer max_id:int min_date:flags.2?int max_date:flags.3?int = messages.AffectedHistory;
messages.readMentions#36e5bf4d flags:# peer:InputPeer top_msg_id:flags.0?int = messages.AffectedHistory;
messages.unpinAllMessages#62dd747 flags:# peer:InputPeer top_msg_id:flags.0?int saved_peer_id:flags.1?InputPeer = messages.AffectedHistory;
messages.readReactions#9ec44f93 flags:# peer:InputPeer top_msg_id:flags.0?int saved_peer_id:flags.1?InputPeer = messages.AffectedHistory;
messages.deleteSavedHistory#4dc5085f flags:# parent_peer:flags.0?InputPeer peer:InputPeer max_id:int min_date:flags.2?int max_date:flags.3?int = messages.AffectedHistory;

channels.deleteParticipantHistory#367544db channel:InputChannel participant:InputPeer = messages.AffectedHistory;
channels.deleteTopicHistory#34435f2d channel:InputChannel top_msg_id:int = messages.AffectedHistory;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.affectedHistory | Affected part of communication history with the user or in a chat. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.deleteHistory | Deletes communication history. |
| messages.readMentions | Mark mentions as read |
| messages.unpinAllMessages | Unpin all pinned messages |
| messages.readReactions | Mark message reactions » as read |
| messages.deleteSavedHistory | Deletes messages from a monoforum topic », or deletes messages forwarded from a specific peer to saved messages ». |
| channels.deleteParticipantHistory | Delete all messages sent by a specific participant of a given supergroup |
| channels.deleteTopicHistory | Delete message history of a forum topic |


