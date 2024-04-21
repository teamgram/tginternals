# Contacts.ResolvedPeer
Peer returned after resolving a @username

```
contacts.resolvedPeer#7f077ad9 peer:Peer chats:Vector<Chat> users:Vector<User> = contacts.ResolvedPeer;

---functions---

contacts.resolveUsername#f93ccba3 username:string = contacts.ResolvedPeer;
contacts.resolvePhone#8af94344 phone:string = contacts.ResolvedPeer;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| contacts.resolvedPeer | Resolved peer |


## Methods
| Method | Description |
| ---- | ----------- |
| contacts.resolveUsername | Resolve a @username to get peer info |
| contacts.resolvePhone | Resolve a phone number to get user info, if their privacy settings allow it. |


