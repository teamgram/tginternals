# messages.InvitedUsers
Contains info about successfully or unsuccessfully invited » users.

```
messages.invitedUsers#7f5defa6 updates:Updates missing_invitees:Vector<MissingInvitee> = messages.InvitedUsers;

---functions---

messages.addChatUser#cbc6d107 chat_id:long user_id:InputUser fwd_limit:int = messages.InvitedUsers;
messages.createChat#92ceddd4 flags:# users:Vector<InputUser> title:string ttl_period:flags.0?int = messages.InvitedUsers;

channels.inviteToChannel#c9e33d54 channel:InputChannel users:Vector<InputUser> = messages.InvitedUsers;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.invitedUsers | Contains info about successfully or unsuccessfully invited » users. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.addChatUser | Adds a user to a chat and sends a service message on it. |
| messages.createChat | Creates a new chat. |
| channels.inviteToChannel | Invite users to a channel/supergroup |


