# requestPeerTypeChat
Choose a chat or supergroup

```
requestPeerTypeChat#c9f06e1b flags:# creator:flags.0?true bot_participant:flags.5?true has_username:flags.3?Bool forum:flags.4?Bool user_admin_rights:flags.1?ChatAdminRights bot_admin_rights:flags.2?ChatAdminRights = RequestPeerType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| creator | flags.0?true | Whether to allow only choosing chats or supergroups that were created by the current user. |
| bot_participant | flags.5?true | Whether to allow only choosing chats or supergroups where the bot is a participant. |
| has_username | flags.3?Bool | If specified, allows only choosing channels with or without a username, according to the value of Bool. |
| forum | flags.4?Bool | If specified, allows only choosing chats or supergroups that are or aren't forums, according to the value of Bool. |
| user_admin_rights | flags.1?ChatAdminRights | If specified, allows only choosing chats or supergroups where the current user is an admin with at least the specified admin rights. |
| bot_admin_rights | flags.2?ChatAdminRights | If specified, allows only choosing chats or supergroups where the bot is an admin with at least the specified admin rights. |


## Type
RequestPeerType

## Related pages
