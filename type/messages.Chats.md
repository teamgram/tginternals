# messages.Chats
Object contains list of chats with auxiliary data.

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;

---functions---

messages.getChats#49e9528f id:Vector<long> = messages.Chats;
messages.getCommonChats#e40ca104 user_id:InputUser max_id:long limit:int = messages.Chats;

channels.getChannels#a7f6bbb id:Vector<InputChannel> = messages.Chats;
channels.getAdminedPublicChannels#f8b036af flags:# by_location:flags.0?true check_limit:flags.1?true = messages.Chats;
channels.getLeftChannels#8341ecc0 offset:int = messages.Chats;
channels.getGroupsForDiscussion#f5dad378 = messages.Chats;
channels.getChannelRecommendations#83b70d97 channel:InputChannel = messages.Chats;

stories.getChatsToSend#a56a8b60 = messages.Chats;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.chats | List of chats with auxiliary data. |
| messages.chatsSlice | Partial list of chats, more would have to be fetched with pagination |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getChats | Returns chat basic info on their IDs. |
| channels.getChannels | Get info about channels/supergroups |
| channels.getAdminedPublicChannels | Get channels/supergroups/geogroups we're admin in. Usually called when the user exceeds the limit for owned public channels/supergroups/geogroups, and the user is given the choice to remove one of his channels/supergroups/geogroups. |
| messages.getCommonChats | Get chats in common with a user |
| channels.getLeftChannels | Get a list of channels/supergroups we left, requires a takeout session, see here » for more info. |
| channels.getGroupsForDiscussion | Get all groups that can be used as discussion groups.Returned basic group chats must be first upgraded to supergroups before they can be set as a discussion group.  To set a returned supergroup as a discussion group, access to its old messages must be enabled using channels.togglePreHistoryHidden, first. |
| stories.getChatsToSend | Obtain a list of channels where the user can post stories |
| channels.getChannelRecommendations | Obtain a list of similarly themed public channels, selected based on similarities in their subscriber bases. |


