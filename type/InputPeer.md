# InputPeer
Peer

```
inputPeerEmpty#7f3b18ea = InputPeer;
inputPeerSelf#7da07ec9 = InputPeer;
inputPeerChat#35a95cb9 chat_id:long = InputPeer;
inputPeerUser#dde8a54c user_id:long access_hash:long = InputPeer;
inputPeerChannel#27bcbbfc channel_id:long access_hash:long = InputPeer;
inputPeerUserFromMessage#a87b0a1c peer:InputPeer msg_id:int user_id:long = InputPeer;
inputPeerChannelFromMessage#bd2a0840 peer:InputPeer msg_id:int channel_id:long = InputPeer;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputPeerEmpty | An empty constructor, no user or chat is defined. |
| inputPeerSelf | Defines the current user. |
| inputPeerChat | Defines a chat for further interaction. |
| inputPeerUser | Defines a user for further interaction. |
| inputPeerChannel | Defines a channel for further interaction. |
| inputPeerUserFromMessage | Defines a min user that was seen in a certain message of a certain chat. |
| inputPeerChannelFromMessage | Defines a min channel that was seen in a certain message of a certain chat. |


## Methods
| Method | Description |
| ---- | ----------- |


