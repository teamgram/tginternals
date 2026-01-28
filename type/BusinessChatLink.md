# BusinessChatLink
Contains info about a business chat deep link » created by the current account.

```
businessChatLink#b4ae666f flags:# link:string message:string entities:flags.0?Vector<MessageEntity> title:flags.1?string views:int = BusinessChatLink;

---functions---

account.createBusinessChatLink#8851e68e link:InputBusinessChatLink = BusinessChatLink;
account.editBusinessChatLink#8c3410af slug:string link:InputBusinessChatLink = BusinessChatLink;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| businessChatLink | Contains info about a business chat deep link » created by the current account. |


## Methods
| Method | Description |
| ---- | ----------- |
| account.createBusinessChatLink | Create a business chat deep link ». |
| account.editBusinessChatLink | Edit a created business chat deep link ». |


