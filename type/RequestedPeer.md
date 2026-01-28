# RequestedPeer
Info about a peer, shared by a user with the currently logged in bot using messages.sendBotRequestedPeer.

```
requestedPeerUser#d62ff46a flags:# user_id:long first_name:flags.0?string last_name:flags.0?string username:flags.1?string photo:flags.2?Photo = RequestedPeer;
requestedPeerChat#7307544f flags:# chat_id:long title:flags.0?string photo:flags.2?Photo = RequestedPeer;
requestedPeerChannel#8ba403e4 flags:# channel_id:long title:flags.0?string username:flags.1?string photo:flags.2?Photo = RequestedPeer;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| requestedPeerUser | Info about a user, shared by a user with the currently logged in bot using messages.sendBotRequestedPeer.All fields except the ID are optional, and will be populated if present on the chosen user, according to the parameters of the requesting inputKeyboardButtonRequestPeer. |
| requestedPeerChat | Info about a chat, shared by a user with the currently logged in bot using messages.sendBotRequestedPeer.All fields except the ID are optional, and will be populated if present on the chosen chat, according to the parameters of the requesting inputKeyboardButtonRequestPeer. |
| requestedPeerChannel | Info about a channel/supergroup, shared by a user with the currently logged in bot using messages.sendBotRequestedPeer.All fields except the ID are optional, and will be populated if present on the chosen channel/supergroup, according to the parameters of the requesting inputKeyboardButtonRequestPeer. |


## Methods
| Method | Description |
| ---- | ----------- |


