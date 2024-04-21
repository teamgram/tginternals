# channels.getAdminedPublicChannels
Get channels/supergroups/geogroups we're admin in. Usually called when the user exceeds the limit for owned public channels/supergroups/geogroups, and the user is given the choice to remove one of his channels/supergroups/geogroups.

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;
---functions---
channels.getAdminedPublicChannels#f8b036af flags:# by_location:flags.0?true check_limit:flags.1?true = messages.Chats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| by_location | flags.0?true | Get geogroups |
| check_limit | flags.1?true | If set and the user has reached the limit of owned public channels/supergroups/geogroups, instead of returning the channel list one of the specified errors will be returned.Useful to check if a new public channel can indeed be created, even before asking the user to enter a channel username to use in channels.checkUsername/channels.updateUsername. |


## Result
messages.Chats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNELS_ADMIN_LOCATED_TOO_MUCH | The user has reached the limit of public geogroups. |
| 400 | CHANNELS_ADMIN_PUBLIC_TOO_MUCH | You're admin of too many public channels, make some channels private to change the username of this channel. |

