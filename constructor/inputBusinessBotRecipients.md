# inputBusinessBotRecipients
Specifies the private chats that a connected business bot » may interact with.

```
inputBusinessBotRecipients#c4e5921e flags:# existing_chats:flags.0?true new_chats:flags.1?true contacts:flags.2?true non_contacts:flags.3?true exclude_selected:flags.5?true users:flags.4?Vector<InputUser> exclude_users:flags.6?Vector<InputUser> = InputBusinessBotRecipients;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| existing_chats | flags.0?true | Selects all existing private chats. |
| new_chats | flags.1?true | Selects all new private chats. |
| contacts | flags.2?true | Selects all private chats with contacts. |
| non_contacts | flags.3?true | Selects all private chats with non-contacts. |
| exclude_selected | flags.5?true | If set, then all private chats except the ones selected by existing_chats, new_chats, contacts, non_contacts and users are chosen. Note that if this flag is set, any values passed in exclude_users will be merged and moved into users by the server. |
| users | flags.4?Vector<InputUser> | Explicitly selected private chats. |
| exclude_users | flags.6?Vector<InputUser> | Identifiers of private chats that are always excluded. |


## Type
InputBusinessBotRecipients

## Related pages
