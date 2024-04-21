# channel
Channel/supergroup info

```
channel#aadfc8f flags:# creator:flags.0?true left:flags.2?true broadcast:flags.5?true verified:flags.7?true megagroup:flags.8?true restricted:flags.9?true signatures:flags.11?true min:flags.12?true scam:flags.19?true has_link:flags.20?true has_geo:flags.21?true slowmode_enabled:flags.22?true call_active:flags.23?true call_not_empty:flags.24?true fake:flags.25?true gigagroup:flags.26?true noforwards:flags.27?true join_to_send:flags.28?true join_request:flags.29?true forum:flags.30?true flags2:# stories_hidden:flags2.1?true stories_hidden_min:flags2.2?true stories_unavailable:flags2.3?true id:long access_hash:flags.13?long title:string username:flags.6?string photo:ChatPhoto date:int restriction_reason:flags.9?Vector<RestrictionReason> admin_rights:flags.14?ChatAdminRights banned_rights:flags.15?ChatBannedRights default_banned_rights:flags.18?ChatBannedRights participants_count:flags.17?int usernames:flags2.0?Vector<Username> stories_max_id:flags2.4?int color:flags2.7?PeerColor profile_color:flags2.8?PeerColor emoji_status:flags2.9?EmojiStatus level:flags2.10?int = Chat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| creator | flags.0?true | Whether the current user is the creator of this channel |
| left | flags.2?true | Whether the current user has left or is not a member of this channel |
| broadcast | flags.5?true | Is this a channel? |
| verified | flags.7?true | Is this channel verified by telegram? |
| megagroup | flags.8?true | Is this a supergroup? |
| restricted | flags.9?true | Whether viewing/writing in this channel for a reason (see restriction_reason |
| signatures | flags.11?true | Whether signatures are enabled (channels) |
| min | flags.12?true | See min |
| scam | flags.19?true | This channel/supergroup is probably a scam |
| has_link | flags.20?true | Whether this channel has a private join link |
| has_geo | flags.21?true | Whether this chanel has a geoposition |
| slowmode_enabled | flags.22?true | Whether slow mode is enabled for groups to prevent flood in chat |
| call_active | flags.23?true | Whether a group call or livestream is currently active |
| call_not_empty | flags.24?true | Whether there's anyone in the group call or livestream |
| fake | flags.25?true | If set, this supergroup/channel was reported by many users as a fake or scam: be careful when interacting with it. |
| gigagroup | flags.26?true | Whether this supergroup is a gigagroup |
| noforwards | flags.27?true | Whether this channel or group is protected, thus does not allow forwarding messages from it |
| join_to_send | flags.28?true | Whether a user needs to join the supergroup before they can send messages: can be false only for discussion groups », toggle using channels.toggleJoinToSend |
| join_request | flags.29?true | Whether a user's join request will have to be approved by administrators, toggle using channels.toggleJoinToSend |
| forum | flags.30?true | Whether this supergroup is a forum |
| flags2 | # | Flags, see TL conditional fields |
| stories_hidden | flags2.1?true | Whether we have hidden all stories posted by this channel ». |
| stories_hidden_min | flags2.2?true | If set, indicates that the stories_hidden flag was not populated, and its value must cannot be relied on; use the previously cached value, or re-fetch the constructor using channels.getChannels to obtain the latest value of the stories_hidden flag. |
| stories_unavailable | flags2.3?true | No stories from the channel are visible. |
| id | long | ID of the channel |
| access_hash | flags.13?long | Access hash |
| title | string | Title |
| username | flags.6?string | Username |
| photo | ChatPhoto | Profile photo |
| date | int | Date when the user joined the supergroup/channel, or if the user isn't a member, its creation date |
| restriction_reason | flags.9?Vector<RestrictionReason> | Contains the reason why access to this channel must be restricted. |
| admin_rights | flags.14?ChatAdminRights | Admin rights of the user in this channel (see rights) |
| banned_rights | flags.15?ChatBannedRights | Banned rights of the user in this channel (see rights) |
| default_banned_rights | flags.18?ChatBannedRights | Default chat rights (see rights) |
| participants_count | flags.17?int | Participant count |
| usernames | flags2.0?Vector<Username> | Additional usernames |
| stories_max_id | flags2.4?int | ID of the maximum read story. |
| color | flags2.7?PeerColor | The channel's accent color. |
| profile_color | flags2.8?PeerColor | The channel's profile color. |
| emoji_status | flags2.9?EmojiStatus | Emoji status |
| level | flags2.10?int | Boost level |


## Type
Chat

## Related pages
