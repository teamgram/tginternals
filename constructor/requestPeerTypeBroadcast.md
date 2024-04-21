# requestPeerTypeBroadcast
Choose a channel

```
requestPeerTypeBroadcast#339bef6c flags:# creator:flags.0?true has_username:flags.3?Bool user_admin_rights:flags.1?ChatAdminRights bot_admin_rights:flags.2?ChatAdminRights = RequestPeerType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| creator | flags.0?true | Whether to allow only choosing channels that were created by the current user. |
| has_username | flags.3?Bool | If specified, allows only choosing channels with or without a username, according to the value of Bool. |
| user_admin_rights | flags.1?ChatAdminRights | If specified, allows only choosing channels where the current user is an admin with at least the specified admin rights. |
| bot_admin_rights | flags.2?ChatAdminRights | If specified, allows only choosing channels where the bot is an admin with at least the specified admin rights. |


## Type
RequestPeerType

## Related pages
