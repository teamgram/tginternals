# Contacts.TopPeers
Top peers

```
contacts.topPeersNotModified#de266ef5 = contacts.TopPeers;
contacts.topPeers#70b772a8 categories:Vector<TopPeerCategoryPeers> chats:Vector<Chat> users:Vector<User> = contacts.TopPeers;
contacts.topPeersDisabled#b52c939d = contacts.TopPeers;

---functions---

contacts.getTopPeers#973478b6 flags:# correspondents:flags.0?true bots_pm:flags.1?true bots_inline:flags.2?true phone_calls:flags.3?true forward_users:flags.4?true forward_chats:flags.5?true groups:flags.10?true channels:flags.15?true offset:int limit:int hash:long = contacts.TopPeers;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| contacts.topPeersNotModified | Top peer info hasn't changed |
| contacts.topPeers | Top peers |
| contacts.topPeersDisabled | Top peers disabled |


## Methods
| Method | Description |
| ---- | ----------- |
| contacts.getTopPeers | Get most used peers |


