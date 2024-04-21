# contacts.Blocked
Info on users from the current user's black list.

```
contacts.blocked#ade1591 blocked:Vector<PeerBlocked> chats:Vector<Chat> users:Vector<User> = contacts.Blocked;
contacts.blockedSlice#e1664194 count:int blocked:Vector<PeerBlocked> chats:Vector<Chat> users:Vector<User> = contacts.Blocked;

---functions---

contacts.getBlocked#9a868f80 flags:# my_stories_from:flags.0?true offset:int limit:int = contacts.Blocked;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| contacts.blocked | Full list of blocked users. |
| contacts.blockedSlice | Incomplete list of blocked users. |


## Methods
| Method | Description |
| ---- | ----------- |
| contacts.getBlocked | Returns the list of blocked users. |


