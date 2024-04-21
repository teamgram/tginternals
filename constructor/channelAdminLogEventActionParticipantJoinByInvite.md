# channelAdminLogEventActionParticipantJoinByInvite
A user joined the supergroup/channel using a specific invite link

```
channelAdminLogEventActionParticipantJoinByInvite#fe9fc158 flags:# via_chatlist:flags.0?true invite:ExportedChatInvite = ChannelAdminLogEventAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| via_chatlist | flags.0?true | The participant joined by importing a chat folder deep link ». |
| invite | ExportedChatInvite | The invite link used to join the supergroup/channel |


## Type
ChannelAdminLogEventAction

## Related pages
