# missingInvitee
Info about why a specific user could not be invited ».

```
missingInvitee#628c9224 flags:# premium_would_allow_invite:flags.0?true premium_required_for_pm:flags.1?true user_id:long = MissingInvitee;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| premium_would_allow_invite | flags.0?true | If set, we could not add the user only because the current account needs to purchase a Telegram Premium subscription to complete the operation. |
| premium_required_for_pm | flags.1?true | If set, we could not add the user because of their privacy settings, and additionally, the current account needs to purchase a Telegram Premium subscription to directly share an invite link with the user via a private message. |
| user_id | long | ID of the user. If neither of the flags below are set, we could not add the user because of their privacy settings, and we can create and directly share an invite link with them using a normal message, instead. |


## Type
MissingInvitee

## Related pages
