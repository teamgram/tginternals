# channel
Channel/supergroup info

```
channel#fe685355 flags:# creator:flags.0?true left:flags.2?true broadcast:flags.5?true verified:flags.7?true megagroup:flags.8?true restricted:flags.9?true signatures:flags.11?true min:flags.12?true scam:flags.19?true has_link:flags.20?true has_geo:flags.21?true slowmode_enabled:flags.22?true call_active:flags.23?true call_not_empty:flags.24?true fake:flags.25?true gigagroup:flags.26?true noforwards:flags.27?true join_to_send:flags.28?true join_request:flags.29?true forum:flags.30?true flags2:# stories_hidden:flags2.1?true stories_hidden_min:flags2.2?true stories_unavailable:flags2.3?true signature_profiles:flags2.12?true autotranslation:flags2.15?true broadcast_messages_allowed:flags2.16?true monoforum:flags2.17?true forum_tabs:flags2.19?true id:long access_hash:flags.13?long title:string username:flags.6?string photo:ChatPhoto date:int restriction_reason:flags.9?Vector<RestrictionReason> admin_rights:flags.14?ChatAdminRights banned_rights:flags.15?ChatBannedRights default_banned_rights:flags.18?ChatBannedRights participants_count:flags.17?int usernames:flags2.0?Vector<Username> stories_max_id:flags2.4?int color:flags2.7?PeerColor profile_color:flags2.8?PeerColor emoji_status:flags2.9?EmojiStatus level:flags2.10?int subscription_until_date:flags2.11?int bot_verification_icon:flags2.13?long send_paid_messages_stars:flags2.14?long linked_monoforum_id:flags2.18?long = Chat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| creator | flags.0?true | Whether the current user is the creator of this channel |
| left | flags.2?true | Whether the current user has left or is not a member of this channel |
| broadcast | flags.5?true | Is this a channel? |
| verified | flags.7?true | Is this channel verified by telegram? |
| megagroup | flags.8?true | Is this a supergroup? Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| restricted | flags.9?true | Whether viewing/writing in this channel for a reason (see restriction_reason) |
| signatures | flags.11?true | Whether signatures are enabled (channels) |
| min | flags.12?true | See min |
| scam | flags.19?true | This channel/supergroup is probably a scam Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| has_link | flags.20?true | Whether this channel has a linked discussion group » (or this supergroup is a channel's discussion group). The actual ID of the linked channel/supergroup is contained in channelFull.linked_chat_id. Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| has_geo | flags.21?true | Whether this chanel has a geoposition |
| slowmode_enabled | flags.22?true | Whether slow mode is enabled for groups to prevent flood in chat. Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| call_active | flags.23?true | Whether a group call or livestream is currently active |
| call_not_empty | flags.24?true | Whether there's anyone in the group call or livestream |
| fake | flags.25?true | If set, this supergroup/channel was reported by many users as a fake or scam: be careful when interacting with it. Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| gigagroup | flags.26?true | Whether this supergroup is a gigagroupChanges to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| noforwards | flags.27?true | Whether this channel or group is protected, thus does not allow forwarding messages from it |
| join_to_send | flags.28?true | Whether a user needs to join the supergroup before they can send messages: can be false only for discussion groups », toggle using channels.toggleJoinToSendChanges to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| join_request | flags.29?true | Whether a user's join request will have to be approved by administrators, toggle using channels.toggleJoinToSendChanges to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| forum | flags.30?true | Whether this supergroup is a forum. Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| flags2 | # | Flags, see TL conditional fields |
| stories_hidden | flags2.1?true | Whether we have hidden all stories posted by this channel ». |
| stories_hidden_min | flags2.2?true | If set, indicates that the stories_hidden flag was not populated, and its value must cannot be relied on; use the previously cached value, or re-fetch the constructor using channels.getChannels to obtain the latest value of the stories_hidden flag. |
| stories_unavailable | flags2.3?true | No stories from the channel are visible. |
| signature_profiles | flags2.12?true | If set, messages sent by admins to this channel will link to the admin's profile (just like with groups). |
| autotranslation | flags2.15?true | If set, autotranslation was enabled for all users by the admin of the channel, as specified here ». |
| broadcast_messages_allowed | flags2.16?true | If set, this channel has an associated monoforum », and its ID is specified in the linked_monoforum_id flag. |
| monoforum | flags2.17?true | If set, this is a monoforum », and the ID of the associated channel is specified in the linked_monoforum_id. |
| forum_tabs | flags2.19?true | If set, enables the tabbed forum UI ». |
| id | long | ID of the channel, see here » for more info and the available ID range. |
| access_hash | flags.13?long | Access hash, see here » for more info |
| title | string | Title |
| username | flags.6?string | Main active username. |
| photo | ChatPhoto | Profile photo |
| date | int | Date when the user joined the supergroup/channel, or if the user isn't a member, its creation date |
| restriction_reason | flags.9?Vector<RestrictionReason> | Contains the reason why access to this channel must be restricted. Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| admin_rights | flags.14?ChatAdminRights | Admin rights of the user in this channel (see rights) |
| banned_rights | flags.15?ChatBannedRights | Banned rights of the user in this channel (see rights) |
| default_banned_rights | flags.18?ChatBannedRights | Default chat rights (see rights) |
| participants_count | flags.17?int | Participant count |
| usernames | flags2.0?Vector<Username> | Additional usernames |
| stories_max_id | flags2.4?int | ID of the maximum read story. |
| color | flags2.7?PeerColor | The channel's accent color. |
| profile_color | flags2.8?PeerColor | The channel's profile color. |
| emoji_status | flags2.9?EmojiStatus | Emoji status |
| level | flags2.10?int | Boost level. Changes to this flag should invalidate the local channelFull cache for this channel/supergroup ID, see here » for more info. |
| subscription_until_date | flags2.11?int | Expiration date of the Telegram Star subscription » the current user has bought to gain access to this channel. |
| bot_verification_icon | flags2.13?long | Describes a bot verification icon ». |
| send_paid_messages_stars | flags2.14?long | If set, this supergroup or monoforum has enabled paid messages », we might need to pay the specified amount of Stars to send messages to it, depending on the configured exceptions: check channelFull.send_paid_messages_stars to see if the currently logged in user actually has to pay or not, see here » for the full flow (only set for the monoforum, not the associated channel). |
| linked_monoforum_id | flags2.18?long | For channels with associated monoforums, the monoforum ID. For Monoforums, the ID of the associated channel. |


## Type
See here » for an implementation of the logic to use when updating the local user peer database.

## Related pages
