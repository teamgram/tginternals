# chatInviteImporter
When and which user joined the chat using a chat invite

```
chatInviteImporter#8c5adfd9 flags:# requested:flags.0?true via_chatlist:flags.3?true user_id:long date:int about:flags.2?string approved_by:flags.1?long = ChatInviteImporter;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| requested | flags.0?true | Whether this user currently has a pending join request » |
| via_chatlist | flags.3?true | The participant joined by importing a chat folder deep link ». |
| user_id | long | The user |
| date | int | When did the user join |
| about | flags.2?string | For users with pending requests, contains bio of the user that requested to join |
| approved_by | flags.1?long | The administrator that approved the join request » of the user |


## Type
ChatInviteImporter

## Related pages
