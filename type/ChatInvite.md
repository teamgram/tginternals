# ChatInvite
Chat invite

```
chatInviteAlready#5a686d7c chat:Chat = ChatInvite;
chatInvite#cde0ec40 flags:# channel:flags.0?true broadcast:flags.1?true public:flags.2?true megagroup:flags.3?true request_needed:flags.6?true verified:flags.7?true scam:flags.8?true fake:flags.9?true title:string about:flags.5?string photo:Photo participants_count:int participants:flags.4?Vector<User> color:int = ChatInvite;
chatInvitePeek#61695cb0 chat:Chat expires:int = ChatInvite;

---functions---

messages.checkChatInvite#3eadb1bb hash:string = ChatInvite;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| chatInviteAlready | The user has already joined this chat |
| chatInvite | Chat invite info |
| chatInvitePeek | A chat invitation that also allows peeking into the group to read messages without joining it. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.checkChatInvite | Check the validity of a chat invite link and get basic info about it |


