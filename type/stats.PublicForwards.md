# Stats.PublicForwards
Contains info about the forwards of a story as a message to public chats and reposts by public channels.

```
stats.publicForwards#93037e20 flags:# count:int forwards:Vector<PublicForward> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stats.PublicForwards;

---functions---

stats.getMessagePublicForwards#5f150144 channel:InputChannel msg_id:int offset:string limit:int = stats.PublicForwards;
stats.getStoryPublicForwards#a6437ef6 peer:InputPeer id:int offset:string limit:int = stats.PublicForwards;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| stats.publicForwards | Contains info about the forwards of a story as a message to public chats and reposts by public channels. |


## Methods
| Method | Description |
| ---- | ----------- |
| stats.getMessagePublicForwards | Obtains a list of messages, indicating to which other public channels was a channel message forwarded.  Will return a list of messages with peer_id equal to the public channel to which this message was forwarded. |
| stats.getStoryPublicForwards | Obtain forwards of a story as a message to public chats and reposts by public channels. |


