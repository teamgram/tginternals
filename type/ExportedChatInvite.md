# ExportedChatInvite
Exported chat invite

```
chatInviteExported#ab4a819 flags:# revoked:flags.0?true permanent:flags.5?true request_needed:flags.6?true link:string admin_id:long date:int start_date:flags.4?int expire_date:flags.1?int usage_limit:flags.2?int usage:flags.3?int requested:flags.7?int title:flags.8?string = ExportedChatInvite;
chatInvitePublicJoinRequests#ed107ab7 = ExportedChatInvite;

---functions---

messages.exportChatInvite#a02ce5d5 flags:# legacy_revoke_permanent:flags.2?true request_needed:flags.3?true peer:InputPeer expire_date:flags.0?int usage_limit:flags.1?int title:flags.4?string = ExportedChatInvite;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| chatInviteExported | Exported chat invite |
| chatInvitePublicJoinRequests | Used in updates and in the channel log to indicate when a user is requesting to join or has joined a discussion group |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.exportChatInvite | Export an invite link for a chat |


