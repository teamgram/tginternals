# contacts.getTopPeers
Get most used peers

```
contacts.topPeersNotModified#de266ef5 = contacts.TopPeers;
contacts.topPeers#70b772a8 categories:Vector<TopPeerCategoryPeers> chats:Vector<Chat> users:Vector<User> = contacts.TopPeers;
contacts.topPeersDisabled#b52c939d = contacts.TopPeers;
---functions---
contacts.getTopPeers#973478b6 flags:# correspondents:flags.0?true bots_pm:flags.1?true bots_inline:flags.2?true phone_calls:flags.3?true forward_users:flags.4?true forward_chats:flags.5?true groups:flags.10?true channels:flags.15?true offset:int limit:int hash:long = contacts.TopPeers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| correspondents | flags.0?true | Users we've chatted most frequently with |
| bots_pm | flags.1?true | Most used bots |
| bots_inline | flags.2?true | Most used inline bots |
| phone_calls | flags.3?true | Most frequently called users |
| forward_users | flags.4?true | Users to which the users often forwards messages to |
| forward_chats | flags.5?true | Chats to which the users often forwards messages to |
| groups | flags.10?true | Often-opened groups and supergroups |
| channels | flags.15?true | Most frequently visited channels |
| offset | int | Offset for pagination |
| limit | int | Maximum number of results to return, see pagination |
| hash | long | Hash for pagination, for more info click here |


## Result
contacts.TopPeers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | TYPES_EMPTY | No top peer type was provided. |

