# channelAdminLogEventsFilter
Filter only certain admin log events

```
channelAdminLogEventsFilter#ea107ae4 flags:# join:flags.0?true leave:flags.1?true invite:flags.2?true ban:flags.3?true unban:flags.4?true kick:flags.5?true unkick:flags.6?true promote:flags.7?true demote:flags.8?true info:flags.9?true settings:flags.10?true pinned:flags.11?true edit:flags.12?true delete:flags.13?true group_call:flags.14?true invites:flags.15?true send:flags.16?true forums:flags.17?true = ChannelAdminLogEventsFilter;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| join | flags.0?true | Join events, including joins using invite links and join requests. |
| leave | flags.1?true | Leave events |
| invite | flags.2?true | Invite events |
| ban | flags.3?true | Ban events |
| unban | flags.4?true | Unban events |
| kick | flags.5?true | Kick events |
| unkick | flags.6?true | Unkick events |
| promote | flags.7?true | Admin promotion events |
| demote | flags.8?true | Admin demotion events |
| info | flags.9?true | Info change events (when about, linked chat, location, photo, stickerset, title or username, slowmode, history TTL settings of a channel gets modified) |
| settings | flags.10?true | Settings change events (invites, hidden prehistory, signatures, default banned rights, forum toggle events) |
| pinned | flags.11?true | Message pin events |
| edit | flags.12?true | Message edit events |
| delete | flags.13?true | Message deletion events |
| group_call | flags.14?true | Group call events |
| invites | flags.15?true | Invite events |
| send | flags.16?true | A message was posted in a channel |
| forums | flags.17?true | Forum-related events |


## Type
ChannelAdminLogEventsFilter

## Related pages
