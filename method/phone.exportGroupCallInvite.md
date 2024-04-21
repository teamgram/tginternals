# phone.exportGroupCallInvite
Get an invite link for a group call or livestream

```
phone.exportedGroupCallInvite#204bd158 link:string = phone.ExportedGroupCallInvite;
---functions---
phone.exportGroupCallInvite#e6aa647f flags:# can_self_unmute:flags.0?true call:InputGroupCall = phone.ExportedGroupCallInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| can_self_unmute | flags.0?true | For livestreams or muted group chats, if set, users that join using this link will be able to speak without explicitly requesting permission by (for example by raising their hand). |
| call | InputGroupCall | The group call |


## Result
phone.ExportedGroupCallInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | PUBLIC_CHANNEL_MISSING | You can only export group call invite links for public chats or channels. |

