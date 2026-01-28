# Peer database

Many constructors in the API need to be stored in a local database upon reception and should only ever be updated reactively (passively) when received via updates or by other means (as specified in the documentation), to avoid overloading the server by continuously requesting changes for the same unchanged information.

user, chat, channel constructors and their full counterparts userFull, chatFull, channelFull are especially important, because they contain important information about users, bots, chats and channels (from now on, peers), and most importantly the access_hash value, required to interact with peers in the API.

This page describes exactly how and when should the local databases of the constructors listed above be refreshed, and contains a more detailed description of basic peer-related concepts.

> For simplicity, the documentation often uses the term "cache" instead of "database" when referring to the peer database, however note that it is recommended to persist received information (or at the very least the id+access hash) to a database, to call methods requiring the access hash and view other peer info without refetching the chat history and peer info after startup.

### Peer info database

```
userEmpty#d3bc4b7a id:long = User;
user#20b1422 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true contact_require_premium:flags2.10?true bot_business:flags2.11?true bot_has_main_app:flags2.13?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor bot_active_users:flags2.12?int bot_verification_icon:flags2.14?long send_paid_messages_stars:flags2.15?long = User;

chatEmpty#29562865 id:long = Chat;
chat#41cbf256 flags:# creator:flags.0?true left:flags.2?true deactivated:flags.5?true call_active:flags.23?true call_not_empty:flags.24?true noforwards:flags.25?true id:long title:string photo:ChatPhoto participants_count:int date:int version:int migrated_to:flags.6?InputChannel admin_rights:flags.14?ChatAdminRights default_banned_rights:flags.18?ChatBannedRights = Chat;
chatForbidden#6592a1a7 id:long title:string = Chat;

channel#fe685355 flags:# creator:flags.0?true left:flags.2?true broadcast:flags.5?true verified:flags.7?true megagroup:flags.8?true restricted:flags.9?true signatures:flags.11?true min:flags.12?true scam:flags.19?true has_link:flags.20?true has_geo:flags.21?true slowmode_enabled:flags.22?true call_active:flags.23?true call_not_empty:flags.24?true fake:flags.25?true gigagroup:flags.26?true noforwards:flags.27?true join_to_send:flags.28?true join_request:flags.29?true forum:flags.30?true flags2:# stories_hidden:flags2.1?true stories_hidden_min:flags2.2?true stories_unavailable:flags2.3?true signature_profiles:flags2.12?true autotranslation:flags2.15?true broadcast_messages_allowed:flags2.16?true monoforum:flags2.17?true forum_tabs:flags2.19?true id:long access_hash:flags.13?long title:string username:flags.6?string photo:ChatPhoto date:int restriction_reason:flags.9?Vector<RestrictionReason> admin_rights:flags.14?ChatAdminRights banned_rights:flags.15?ChatBannedRights default_banned_rights:flags.18?ChatBannedRights participants_count:flags.17?int usernames:flags2.0?Vector<Username> stories_max_id:flags2.4?int color:flags2.7?PeerColor profile_color:flags2.8?PeerColor emoji_status:flags2.9?EmojiStatus level:flags2.10?int subscription_until_date:flags2.11?int bot_verification_icon:flags2.13?long send_paid_messages_stars:flags2.14?long linked_monoforum_id:flags2.18?long = Chat;
channelForbidden#17d493d5 flags:# broadcast:flags.5?true megagroup:flags.8?true id:long access_hash:long title:string until_date:flags.16?int = Chat;

inputUserEmpty#b98886cf = InputUser;
inputUserSelf#f7c1b13f = InputUser;
inputUser#f21158c6 user_id:long access_hash:long = InputUser;
inputUserFromMessage#1da448e2 peer:InputPeer msg_id:int user_id:long = InputUser;

// No inputChat, just a long is used (because basic chats don't have access hashes)

inputChannelEmpty#ee8c1e86 = InputChannel;
inputChannel#f35aec28 channel_id:long access_hash:long = InputChannel;
inputChannelFromMessage#5b934f9d peer:InputPeer msg_id:int channel_id:long = InputChannel;

inputPeerEmpty#7f3b18ea = InputPeer;
inputPeerSelf#7da07ec9 = InputPeer;
inputPeerChat#35a95cb9 chat_id:long = InputPeer;
inputPeerUser#dde8a54c user_id:long access_hash:long = InputPeer;
inputPeerChannel#27bcbbfc channel_id:long access_hash:long = InputPeer;
inputPeerUserFromMessage#a87b0a1c peer:InputPeer msg_id:int user_id:long = InputPeer;
inputPeerChannelFromMessage#bd2a0840 peer:InputPeer msg_id:int channel_id:long = InputPeer;

---functions---

users.getUsers#d91a548 id:Vector<InputUser> = Vector<User>;
messages.getChats#49e9528f id:Vector<long> = messages.Chats;
channels.getChannels#a7f6bbb id:Vector<InputChannel> = messages.Chats;
```

The peer info database contains the following information:

- The peer ID »

- The access hash »

- Other info »

And it must be populated as follows:

- By saving received user, chat, channel constructors »

- By handling certain updates »

- By manual refreshes »

Example implementation: tdlib.

#### Saving constructors

The peer info database needs to be updated every time a new constructor of type user, chat and channel (and their forbidden counterparts, used for peers that the user can't access, but can view basic info about) is received.

These constructors are received when interacting with the API (i.e. in common chats, through the search function, username resolution, temporary profile links, and so on...).

Unless specified otherwise (see the constructor pages for the special cases), when updating the local peer database, all fields from the newly received constructor take priority over the old constructor cached locally (including by removing fields that aren't set in the new constructor).

#### Handling certain updates

The following updates should trigger an update of a small subset of the info contained in the peer database (both non-full and full variants):

- updateUserStatus - Update user.status

- updateUserName- Update user.first_name/last_name/username/usernames

- updatePeerBlocked - Update userFull.blocked, channelFull.blocked

- updatePeerSettings - Update userFull.settings

- updatePeerWallpaper - Update userFull.wallpaper, channelFull.wallpaper

- updateUserEmojiStatus - Update user.emoji_status

- updateChatParticipants - Update chat.participants_count, chatFull.participants.

- updateChatParticipant - Update chat.participants_count, chatFull.participants.

- updateChannelAvailableMessages - Update channel.hidden_prehistory

#### Manual refreshes

For performance reasons, the server will not always send updates containing updated information about all peers: for this reason, information about already cached peers may be refreshed manually in certain conditions using the bulked users.getUsers, messages.getChats, channels.getChannels methods, all requiring the previously cached access_hash.

The following list is non-exhaustive, and clients may choose to refresh peer information in some other conditions as well (i.e. when opening the profile page, etc).

- When fetching info about one of the following internal user IDs, if the info isn't already cached or if the cached info is min: 777000 (service notifications user), 1271266957 (replies bot), 1087968824 (anonymous bot), 136817688 (channel bot), 5434988373 (antispam bot).

- Info about these IDs may be fetched with the zero access hash even by users.

- After invoking bots.setBotInfo after changing name (but not the about or the description, as changing those fields already triggers a refresh of the full info database, and with it the peer database), for the bot whose info we changed

- After receiving a CHAT_FORWARDS_RESTRICTED error when forwarding messages from a chat, to refresh info about the source chat (i.e. the fact that we received this error means that the client didn't locally prevent the user from forwarding a message from the protected chat, because the locally cached channel.noforwards/chat.noforwards flag is out of date).

- After receiving a CHAT_GUEST_SEND_FORBIDDEN error when sending messages to a discussion group, to refresh info about the discussion group (i.e. the fact that we received this error means that the client didn't locally prevent the non-member user from sending a message to a discussion group where only members can send messages, because the locally cached channel.join_to_send flag is out of date).

- After receiving a USER_NOT_PARTICIPANT error when calling channels.leaveChannel, to refresh info about the channel/supergroup (i.e. the fact that we received this error means that the client tried to leave a channel/supergroup they're not a member of, and the client didn't try to prevent this locally because its channel constructor is out of date).

- After invoking the following methods (both if the call succeds and after receiving a USERNAME_NOT_MODIFIED error, which is also a success):

- account.toggleUsername, account.reorderUsernames - For ourselves

- bots.toggleUsername, bots.reorderUsernames - For the bot whose username we updated

- channels.toggleUsername, channels.reorderUsernames - For the channel whose username we updated

- Info should only be manually refreshed with a call to users.getUsers, channels.getChannels if the new username order/active username cannot be applied locally (i.e. the method call successfully set as active some username that isn't associated to the peer in our local cache, and so on), otherwise the username and usernames fields of the peer info database should be updated locally, using the info that was passed to the toggle/reorder methods by the user.

- After invoking the following methods, if the user for whom we set the profile photo is not returned in photos.photo.users:

- photos.updateProfilePhoto

- photos.uploadProfilePhoto

- photos.uploadContactProfilePhoto - Only if suggest is not set

- After invoking photos.deletePhotos, if the local cache doesn't have any more photos left for the current user after removing the ones passed to the method.

- After failing to download a peer photo.

- contacts.getStatuses should be invoked by clients every 70000-100000 seconds to update the user.status field of contacts.

- The exact contact status polling interval should be randomly chosen between 70000 and 100000, and re-chosen every time contacts.getStatuses is invoked.

- If a contacts.getStatuses query fails, repeat the method call after 5 to 10 seconds.

#### Peer ID

The peer id is a unique 64-bit ID used to identify a specific user, chat or channel.

This field should be used as primary key in the channel, chat and user databases.

Note that the ID sequences of users, chats and channels overlap, so you must either:

- Use separate tables/hashmaps for users, chats and channels OR

- Transform the peer IDs to bot API IDs as specified here », which will allow you to use a single ID sequence (and database) for all three peer types, maintaining uniqueness.

- In this case, a single table can be used for all peer types, but since the structures of the constructors are different, to avoid useless typechecks it might be a good idea to use three tables, as with the first approach.

Click on the following links to view the available MTProto ID ranges for the various chat types, and info on how to convert them to single bot API range:

- Users »

- Chats »

- Supergroups/channels »

- Monoforums »

It's a good idea to transform peer IDs to bot API IDs even if you do decide to use separate databases, as it will make IDs more visually recognizable both for you and your users, as well as guarantee compatibility with the bot API.

#### Access hash

The access_hash is the second most important field stored in the peer database, used to generate InputPeer, inputUser, inputChannel constructors used to interact with peers in the API.
Note that chats (basic groups ») do not have or need an access hash.
users and channels (supergroups and channels ») have an access hash, and it can come in various flavors:

- Full access hash: can be used everywhere in the API.

- Min access hash: received from min constructors », can only be used to fetch profile pictures using inputPeerPhotoFileLocation ».

- From-message access hash: not a real access hash, constructed as specified here », must be used when only a min access hash is available locally, but a full access hash is required.

- Zero access hash: equal to 0, must be used by bots when only a min access hash (or no access hash) is available locally, but a full access hash is required.

The access hash versions listed above are listed in descending priority, and if a version with higher priority is currently cached, it must not be overwritten with a lower priority version.

Access hashes are received when interacting with the API (i.e. in common chats, through the search function, username resolution, temporary profile links, and so on...): if you have only a user/channel/supergroup ID without any kind of access hash, you cannot interact with that peer.
Access hashes may not be reused across different accounts or different sessions of the same account.
This is a core spam prevention feature of Telegram.

Clients and client APIs should avoid exposing access hashes to users, as they cannot be reused outside of the current session, and the user should not be burdened with storing them, when the client can perfectly do the job by itself.

Note: some other, non-peer-related constructors (i.e. not user, chat or channel) may also contain access hashes, which should be stored in a different database.

#### Other info

Various other fields commonly used by the client, as specified in the constructor pages (user, chat and channel).
As specified in the constructor docs, some of the fields must not be overwritten if a min constructor is received, and a change in some other fields must trigger invalidation of the full info database ».

### Full info database

```
users.userFull#3b6d152e full_user:UserFull chats:Vector<Chat> users:Vector<User> = users.UserFull;
messages.chatFull#e5d7d19c full_chat:ChatFull chats:Vector<Chat> users:Vector<User> = messages.ChatFull;

userFull#c577b5ad flags:# blocked:flags.0?true phone_calls_available:flags.4?true phone_calls_private:flags.5?true can_pin_message:flags.7?true has_scheduled:flags.12?true video_calls_available:flags.13?true voice_messages_forbidden:flags.20?true translations_disabled:flags.23?true stories_pinned_available:flags.26?true blocked_my_stories_from:flags.27?true wallpaper_overridden:flags.28?true contact_require_premium:flags.29?true read_dates_private:flags.30?true flags2:# sponsored_enabled:flags2.7?true can_view_revenue:flags2.9?true bot_can_manage_emoji_status:flags2.10?true display_gifts_button:flags2.16?true id:long about:flags.1?string settings:PeerSettings personal_photo:flags.21?Photo profile_photo:flags.2?Photo fallback_photo:flags.22?Photo notify_settings:PeerNotifySettings bot_info:flags.3?BotInfo pinned_msg_id:flags.6?int common_chats_count:int folder_id:flags.11?int ttl_period:flags.14?int theme:flags.15?ChatTheme private_forward_name:flags.16?string bot_group_admin_rights:flags.17?ChatAdminRights bot_broadcast_admin_rights:flags.18?ChatAdminRights wallpaper:flags.24?WallPaper stories:flags.25?PeerStories business_work_hours:flags2.0?BusinessWorkHours business_location:flags2.1?BusinessLocation business_greeting_message:flags2.2?BusinessGreetingMessage business_away_message:flags2.3?BusinessAwayMessage business_intro:flags2.4?BusinessIntro birthday:flags2.5?Birthday personal_channel_id:flags2.6?long personal_channel_message:flags2.6?int stargifts_count:flags2.8?int starref_program:flags2.11?StarRefProgram bot_verification:flags2.12?BotVerification send_paid_messages_stars:flags2.14?long disallowed_gifts:flags2.15?DisallowedGiftsSettings stars_rating:flags2.17?StarsRating stars_my_pending_rating:flags2.18?StarsRating stars_my_pending_rating_date:flags2.18?int main_tab:flags2.20?ProfileTab saved_music:flags2.21?Document = UserFull;
chatFull#2633421b flags:# can_set_username:flags.7?true has_scheduled:flags.8?true translations_disabled:flags.19?true id:long about:string participants:ChatParticipants chat_photo:flags.2?Photo notify_settings:PeerNotifySettings exported_invite:flags.13?ExportedChatInvite bot_info:flags.3?Vector<BotInfo> pinned_msg_id:flags.6?int folder_id:flags.11?int call:flags.12?InputGroupCall ttl_period:flags.14?int groupcall_default_join_as:flags.15?Peer theme_emoticon:flags.16?string requests_pending:flags.17?int recent_requesters:flags.17?Vector<long> available_reactions:flags.18?ChatReactions reactions_limit:flags.20?int = ChatFull;
channelFull#e4e0b29d flags:# can_view_participants:flags.3?true can_set_username:flags.6?true can_set_stickers:flags.7?true hidden_prehistory:flags.10?true can_set_location:flags.16?true has_scheduled:flags.19?true can_view_stats:flags.20?true blocked:flags.22?true flags2:# can_delete_channel:flags2.0?true antispam:flags2.1?true participants_hidden:flags2.2?true translations_disabled:flags2.3?true stories_pinned_available:flags2.5?true view_forum_as_messages:flags2.6?true restricted_sponsored:flags2.11?true can_view_revenue:flags2.12?true paid_media_allowed:flags2.14?true can_view_stars_revenue:flags2.15?true paid_reactions_available:flags2.16?true stargifts_available:flags2.19?true paid_messages_available:flags2.20?true id:long about:string participants_count:flags.0?int admins_count:flags.1?int kicked_count:flags.2?int banned_count:flags.2?int online_count:flags.13?int read_inbox_max_id:int read_outbox_max_id:int unread_count:int chat_photo:Photo notify_settings:PeerNotifySettings exported_invite:flags.23?ExportedChatInvite bot_info:Vector<BotInfo> migrated_from_chat_id:flags.4?long migrated_from_max_id:flags.4?int pinned_msg_id:flags.5?int stickerset:flags.8?StickerSet available_min_id:flags.9?int folder_id:flags.11?int linked_chat_id:flags.14?long location:flags.15?ChannelLocation slowmode_seconds:flags.17?int slowmode_next_send_date:flags.18?int stats_dc:flags.12?int pts:int call:flags.21?InputGroupCall ttl_period:flags.24?int pending_suggestions:flags.25?Vector<string> groupcall_default_join_as:flags.26?Peer theme_emoticon:flags.27?string requests_pending:flags.28?int recent_requesters:flags.28?Vector<long> default_send_as:flags.29?Peer available_reactions:flags.30?ChatReactions reactions_limit:flags2.13?int stories:flags2.4?PeerStories wallpaper:flags2.7?WallPaper boosts_applied:flags2.8?int boosts_unrestrict:flags2.9?int emojiset:flags2.10?StickerSet bot_verification:flags2.17?BotVerification stargifts_count:flags2.18?int send_paid_messages_stars:flags2.21?long main_tab:flags2.22?ProfileTab = ChatFull;

---functions---

users.getFullUser#b60f5918 id:InputUser = users.UserFull;
messages.getFullChat#aeb00b34 chat_id:long = messages.ChatFull;
channels.getFullChannel#8736a09 channel:InputChannel = messages.ChatFull;
```

Example implementation: tdlib.

The full info database contains info from the userFull, chatFull and channelFull constructors.

To populate the full info database for a peer, invoke users.getFullUser, messages.getFullChat, channels.getFullChannel, all requiring the previously cached access_hash ».

Invalidate only userFull and channelFull entries 60 seconds after they are stored.

Refresh the full info database when the client needs some data from a full constructor, and there is no entry already in the database, or the required entry was invalidated by the TTL, or if:

- Some event (specified here ») changes the value of a very specific subset of fields of an entry in the (non-full!) peer info database ».

- See the documentation in the user and channel constructor pages for more info (search for the keyword "invalidate").

- When receiving an updateUser, updateChat, updateChannel, and some other updates, as specified here »

- After invoking bots.setBotInfo (even on error) after changing about or description (but not name), for the bot whose info we changed.

- After invoking messages.setChatWallPaper to remove the wallpaper and receiving an error, for the peer whose wallpapers we tried to change, to fetch the correct and updated wallpaper settings.

- After invoking messages.setChatAvailableReactions and getting an error different from CHAT_NOT_MODIFIED, for the peer whose reaction settings we tried to change.

- After receiving a SEND_AS_PEER_INVALID error from any method that interacts with a group/supergroup: refresh info about the destination, to see which channel peers can be used to send messages to the group/supergroup through send_as.

- If chat.photo is not equal to chatFull.chat_photo

- The channelFull.linked_chat_id of channnel/supergroup A is updated to point to channel/supergroup B, but the channelFull.linked_chat_id of channel/supergroup B does not point to channel/supergroup A, refresh the channelFull of channel/supergroup B.

- Info about a bot that is a participant to the channel/supergroup is fetched by other means, but the bot is not contained in channelFull.bot_info.

- If channelFull.participants_count is less than channelFull.admins_count after a local update of the admin list by other means.

- If the currently logged in user's inputPrivacyKeyStatusTimestamp privacy setting » was changed, refresh the entire userFull cache for all users.

- After receiving an error different from USER_NOT_PARTICIPANT when calling channels.leaveChannel

- If the profile picture is updated or removed

- After successfully invoking any of the following methods, for the bot in question:

- bots.deletePreviewMedia

- After invoking any of the following methods (successfully or not):

- bots.setBotGroupDefaultAdminRights - For the bot

- bots.setBotBroadcastDefaultAdminRights - For the bot

- channels.inviteToChannel - For the channel/supergroup

- channels.editAdmin - For the channel/supergroup

- channels.editCreator - For the channel/supergroup

- When receiving a CHANNEL_PRIVATE or CHANNEL_PUBLIC_GROUP_NA RPC error.

- When a channel is made private/public (where previously it was public/private. public=has at least one username, private=has no usernames).

- If we banned a chat/supergroup participant specifying a chatBannedRights.until_date, the full cache of the chat/supergroup should be refreshed for the admin at until_date.

The above list is non-exhaustive, and clients may choose to refresh peer information in some other conditions as well (i.e. when opening the profile page, etc).

### Quality of life checks

Note the following: peer information is also used for quality-of-life improvements, i.e. to directly prevent the user from doing an operation that is denied by the peer information, instead of allowing the operation and then showing an error.

These improvements should be implemented by all clients, however, the server will also always prevent the user from doing illegal operations, by emitting an appropriate RPC error, as sometimes it is still possible to make an illegal operation, even if a local check is implemented (see below).

Instead of (or along with) preventing users from doing illegal operations on the client side, clients should always provide localized versions of errors returned by the server (as listed in the JSON file downloadable from the RPC error page), to inform the user as to why an attempted operation has failed.

In other words, if the client didn't prevent the failed method call locally because:

- It does not implement a local check for simplicity or

- It does implement a local check, but:

- Peer info is outdated or

- An update was sent by the server for the peer info, but it wasn't applied in time due to an (unavoidable!) race condition between the server sending the update and the client sending the query.

- Other unspecified reasons (a new check introduced in a future layer by a new feature, etc...)

...it should still let the user know why the query failed, based on the description of the RPC error (if available in the JSON error database, otherwise by showing the RPC error itself).

