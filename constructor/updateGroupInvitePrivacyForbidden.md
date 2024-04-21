# updateGroupInvitePrivacyForbidden
0-N updates of this type may be returned only when invoking messages.addChatUser, channels.inviteToChannel or messages.createChat: it indicates we couldn't add a user to a chat because of their privacy settings; if required, an invite link can be shared with the user, instead.

```
updateGroupInvitePrivacyForbidden#ccf08ad6 user_id:long = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | long | ID of the user we couldn't add. |


## Type
Update

## Related pages
