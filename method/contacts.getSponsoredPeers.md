# contacts.getSponsoredPeers
Obtain a list of sponsored peer search results for a given query

```
contacts.sponsoredPeersEmpty#ea32b4b1 = contacts.SponsoredPeers;
contacts.sponsoredPeers#eb032884 peers:Vector<SponsoredPeer> chats:Vector<Chat> users:Vector<User> = contacts.SponsoredPeers;
---functions---
contacts.getSponsoredPeers#b6c8c393 q:string = contacts.SponsoredPeers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| q | string | The query |


## Result
contacts.SponsoredPeers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SEARCH_QUERY_EMPTY | The search query is empty. |

