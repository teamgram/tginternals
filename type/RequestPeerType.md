# RequestPeerType
Filtering criteria to use for the peer selection list shown to the user.

```
requestPeerTypeUser#5f3b8a00 flags:# bot:flags.0?Bool premium:flags.1?Bool = RequestPeerType;
requestPeerTypeChat#c9f06e1b flags:# creator:flags.0?true bot_participant:flags.5?true has_username:flags.3?Bool forum:flags.4?Bool user_admin_rights:flags.1?ChatAdminRights bot_admin_rights:flags.2?ChatAdminRights = RequestPeerType;
requestPeerTypeBroadcast#339bef6c flags:# creator:flags.0?true has_username:flags.3?Bool user_admin_rights:flags.1?ChatAdminRights bot_admin_rights:flags.2?ChatAdminRights = RequestPeerType;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| requestPeerTypeUser | Choose a user. |
| requestPeerTypeChat | Choose a chat or supergroup |
| requestPeerTypeBroadcast | Choose a channel |


## Methods
| Method | Description |
| ---- | ----------- |


