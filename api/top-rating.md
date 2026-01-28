# Top peer rating

If enabled, the rating of top peers indicates the relevance of a frequently used peer in a certain category (frequently messaged users, frequently used bots, inline bots, frequently visited channels and so on).

Schema:

```
topPeerCategoryBotsPM#ab661b5b = TopPeerCategory;
topPeerCategoryBotsInline#148677e2 = TopPeerCategory;
topPeerCategoryCorrespondents#637b7ed = TopPeerCategory;
topPeerCategoryGroups#bd17a14a = TopPeerCategory;
topPeerCategoryChannels#161d9628 = TopPeerCategory;
topPeerCategoryPhoneCalls#1e76a78c = TopPeerCategory;
topPeerCategoryForwardUsers#a8406ca9 = TopPeerCategory;
topPeerCategoryForwardChats#fbeec0f0 = TopPeerCategory;
topPeerCategoryBotsApp#fd9e7bec = TopPeerCategory;

topPeer#edcdc05b peer:Peer rating:double = TopPeer;

topPeerCategoryPeers#fb834291 category:TopPeerCategory count:int peers:Vector<TopPeer> = TopPeerCategoryPeers;

contacts.topPeersNotModified#de266ef5 = contacts.TopPeers;
contacts.topPeers#70b772a8 categories:Vector<TopPeerCategoryPeers> chats:Vector<Chat> users:Vector<User> = contacts.TopPeers;
contacts.topPeersDisabled#b52c939d = contacts.TopPeers;

---functions---

contacts.toggleTopPeers#8514bdda enabled:Bool = Bool;
contacts.getTopPeers#973478b6 flags:# correspondents:flags.0?true bots_pm:flags.1?true bots_inline:flags.2?true phone_calls:flags.3?true forward_users:flags.4?true forward_chats:flags.5?true groups:flags.10?true channels:flags.15?true bots_app:flags.16?true offset:int limit:int hash:long = contacts.TopPeers;
contacts.resetTopPeerRating#1ae373ac category:TopPeerCategory peer:InputPeer = Bool;
```

The rate delta is computed by taking the time delta between the last time the user used a certain peer and the last time the rating for that peer was received through contacts.getTopPeers and dividing it by the exponential decay from config.

Specifically, clients should:

```
topPeer.rating += e^((dateOpened - normalizeRate) / config.rating_e_decay)
```

Use contacts.toggleTopPeers to enable or disable top peer ratings.
Use contacts.resetTopPeerRating to reset the top peer rating of a certain peer, in a certain category.

