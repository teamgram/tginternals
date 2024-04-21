# contacts.getBlocked
Returns the list of blocked users.

```
contacts.blocked#ade1591 blocked:Vector<PeerBlocked> chats:Vector<Chat> users:Vector<User> = contacts.Blocked;
contacts.blockedSlice#e1664194 count:int blocked:Vector<PeerBlocked> chats:Vector<Chat> users:Vector<User> = contacts.Blocked;
---functions---
contacts.getBlocked#9a868f80 flags:# my_stories_from:flags.0?true offset:int limit:int = contacts.Blocked;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| my_stories_from | flags.0?true | Whether to fetch the story blocklist; if not set, will fetch the main blocklist. See here » for differences between the two. |
| offset | int | The number of list elements to be skipped |
| limit | int | The number of list elements to be returned |


## Result
contacts.Blocked

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

