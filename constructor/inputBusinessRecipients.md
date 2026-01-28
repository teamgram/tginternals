# inputBusinessRecipients
Specifies the chats that can receive Telegram Business away » and greeting » messages.

```
inputBusinessRecipients#6f8b32aa flags:# existing_chats:flags.0?true new_chats:flags.1?true contacts:flags.2?true non_contacts:flags.3?true exclude_selected:flags.5?true users:flags.4?Vector<InputUser> = InputBusinessRecipients;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| existing_chats | flags.0?true | All existing private chats. |
| new_chats | flags.1?true | All new private chats. |
| contacts | flags.2?true | All private chats with contacts. |
| non_contacts | flags.3?true | All private chats with non-contacts. |
| exclude_selected | flags.5?true | If set, inverts the selection. |
| users | flags.4?Vector<InputUser> | Only private chats with the specified users. |


## Type


## Related pages
