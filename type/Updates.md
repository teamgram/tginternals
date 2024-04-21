# Updates
Object which is perceived by the client without a call on its part when an event occurs.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;

---functions---

contacts.deleteContacts#96a0e00 id:Vector<InputUser> = Updates;
contacts.addContact#e8f463d0 flags:# add_phone_privacy_exception:flags.0?true id:InputUser first_name:string last_name:string phone:string = Updates;
contacts.acceptContact#f831a20f id:InputUser = Updates;
contacts.getLocated#d348bc44 flags:# background:flags.1?true geo_point:InputGeoPoint self_expires:flags.0?int = Updates;
contacts.blockFromReplies#29a8962c flags:# delete_message:flags.0?true delete_history:flags.1?true report_spam:flags.2?true msg_id:int = Updates;

messages.sendMessage#280d096f flags:# no_webpage:flags.1?true silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
messages.sendMedia#72ccc23d flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
messages.forwardMessages#c661bbc4 flags:# silent:flags.5?true background:flags.6?true with_my_score:flags.8?true drop_author:flags.11?true drop_media_captions:flags.12?true noforwards:flags.14?true from_peer:InputPeer id:Vector<int> random_id:Vector<long> to_peer:InputPeer top_msg_id:flags.9?int schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
messages.editChatTitle#73783ffd chat_id:long title:string = Updates;
messages.editChatPhoto#35ddd674 chat_id:long photo:InputChatPhoto = Updates;
messages.addChatUser#f24753e3 chat_id:long user_id:InputUser fwd_limit:int = Updates;
messages.deleteChatUser#a2185cab flags:# revoke_history:flags.0?true chat_id:long user_id:InputUser = Updates;
messages.createChat#34a818 flags:# users:Vector<InputUser> title:string ttl_period:flags.0?int = Updates;
messages.importChatInvite#6c50051c hash:string = Updates;
messages.startBot#e6df7378 bot:InputUser peer:InputPeer random_id:long start_param:string = Updates;
messages.migrateChat#a2875319 chat_id:long = Updates;
messages.sendInlineBotResult#f7bc68ba flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true hide_via:flags.11?true peer:InputPeer reply_to:flags.0?InputReplyTo random_id:long query_id:long id:string schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
messages.editMessage#48f71778 flags:# no_webpage:flags.1?true invert_media:flags.16?true peer:InputPeer id:int message:flags.11?string media:flags.14?InputMedia reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.15?int = Updates;
messages.getAllDrafts#6a3f8d65 = Updates;
messages.setGameScore#8ef8ecc0 flags:# edit_message:flags.0?true force:flags.1?true peer:InputPeer id:int user_id:InputUser score:int = Updates;
messages.sendScreenshotNotification#a1405817 peer:InputPeer reply_to:InputReplyTo random_id:long = Updates;
messages.sendMultiMedia#456e8987 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo multi_media:Vector<InputSingleMedia> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
messages.updatePinnedMessage#d2aaf7ec flags:# silent:flags.0?true unpin:flags.1?true pm_oneside:flags.2?true peer:InputPeer id:int = Updates;
messages.sendVote#10ea6184 peer:InputPeer msg_id:int options:Vector<bytes> = Updates;
messages.getPollResults#73bb643b peer:InputPeer msg_id:int = Updates;
messages.editChatDefaultBannedRights#a5866b41 peer:InputPeer banned_rights:ChatBannedRights = Updates;
messages.sendScheduledMessages#bd38850a peer:InputPeer id:Vector<int> = Updates;
messages.deleteScheduledMessages#59ae2b16 peer:InputPeer id:Vector<int> = Updates;
messages.setHistoryTTL#b80e5fe4 peer:InputPeer period:int = Updates;
messages.setChatTheme#e63be13f peer:InputPeer emoticon:string = Updates;
messages.hideChatJoinRequest#7fe7e815 flags:# approved:flags.0?true peer:InputPeer user_id:InputUser = Updates;
messages.hideAllChatJoinRequests#e085f4ea flags:# approved:flags.0?true peer:InputPeer link:flags.1?string = Updates;
messages.toggleNoForwards#b11eafa2 peer:InputPeer enabled:Bool = Updates;
messages.sendReaction#d30d78d4 flags:# big:flags.1?true add_to_recent:flags.2?true peer:InputPeer msg_id:int reaction:flags.0?Vector<Reaction> = Updates;
messages.getMessagesReactions#8bba90e6 peer:InputPeer id:Vector<int> = Updates;
messages.setChatAvailableReactions#feb16771 peer:InputPeer available_reactions:ChatReactions = Updates;
messages.sendWebViewData#dc0242c8 bot:InputUser random_id:long button_text:string data:string = Updates;
messages.getExtendedMedia#84f80814 peer:InputPeer id:Vector<int> = Updates;
messages.sendBotRequestedPeer#91b2d060 peer:InputPeer msg_id:int button_id:int requested_peers:Vector<InputPeer> = Updates;
messages.setChatWallPaper#8ffacae1 flags:# for_both:flags.3?true revert:flags.4?true peer:InputPeer wallpaper:flags.0?InputWallPaper settings:flags.2?WallPaperSettings id:flags.1?int = Updates;

channels.createChannel#91006707 flags:# broadcast:flags.0?true megagroup:flags.1?true for_import:flags.3?true forum:flags.5?true title:string about:string geo_point:flags.2?InputGeoPoint address:flags.2?string ttl_period:flags.4?int = Updates;
channels.editAdmin#d33c8902 channel:InputChannel user_id:InputUser admin_rights:ChatAdminRights rank:string = Updates;
channels.editTitle#566decd0 channel:InputChannel title:string = Updates;
channels.editPhoto#f12e57c9 channel:InputChannel photo:InputChatPhoto = Updates;
channels.joinChannel#24b524c5 channel:InputChannel = Updates;
channels.leaveChannel#f836aa95 channel:InputChannel = Updates;
channels.inviteToChannel#199f3a6c channel:InputChannel users:Vector<InputUser> = Updates;
channels.deleteChannel#c0111fe3 channel:InputChannel = Updates;
channels.toggleSignatures#1f69b606 channel:InputChannel enabled:Bool = Updates;
channels.editBanned#96e6cd81 channel:InputChannel participant:InputPeer banned_rights:ChatBannedRights = Updates;
channels.deleteHistory#9baa9647 flags:# for_everyone:flags.0?true channel:InputChannel max_id:int = Updates;
channels.togglePreHistoryHidden#eabbb94c channel:InputChannel enabled:Bool = Updates;
channels.editCreator#8f38cd1f channel:InputChannel user_id:InputUser password:InputCheckPasswordSRP = Updates;
channels.toggleSlowMode#edd49ef0 channel:InputChannel seconds:int = Updates;
channels.convertToGigagroup#b290c69 channel:InputChannel = Updates;
channels.toggleJoinToSend#e4cb9580 channel:InputChannel enabled:Bool = Updates;
channels.toggleJoinRequest#4c2985b6 channel:InputChannel enabled:Bool = Updates;
channels.toggleForum#a4298b29 channel:InputChannel enabled:Bool = Updates;
channels.createForumTopic#f40c0224 flags:# channel:InputChannel title:string icon_color:flags.0?int icon_emoji_id:flags.3?long random_id:long send_as:flags.2?InputPeer = Updates;
channels.editForumTopic#f4dfa185 flags:# channel:InputChannel topic_id:int title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = Updates;
channels.updatePinnedForumTopic#6c2d9026 channel:InputChannel topic_id:int pinned:Bool = Updates;
channels.reorderPinnedForumTopics#2950a18f flags:# force:flags.0?true channel:InputChannel order:Vector<int> = Updates;
channels.toggleAntiSpam#68f3e4eb channel:InputChannel enabled:Bool = Updates;
channels.toggleParticipantsHidden#6a6e7854 channel:InputChannel enabled:Bool = Updates;
channels.updateColor#d8aa3671 flags:# for_profile:flags.1?true channel:InputChannel color:flags.2?int background_emoji_id:flags.0?long = Updates;
channels.toggleViewForumAsMessages#9738bb15 channel:InputChannel enabled:Bool = Updates;
channels.updateEmojiStatus#f0d3e6a8 channel:InputChannel emoji_status:EmojiStatus = Updates;

phone.discardCall#b2cbc1c0 flags:# video:flags.0?true peer:InputPhoneCall duration:int reason:PhoneCallDiscardReason connection_id:long = Updates;
phone.setCallRating#59ead627 flags:# user_initiative:flags.0?true peer:InputPhoneCall rating:int comment:string = Updates;
phone.createGroupCall#48cdc6d8 flags:# rtmp_stream:flags.2?true peer:InputPeer random_id:int title:flags.0?string schedule_date:flags.1?int = Updates;
phone.joinGroupCall#b132ff7b flags:# muted:flags.0?true video_stopped:flags.2?true call:InputGroupCall join_as:InputPeer invite_hash:flags.1?string params:DataJSON = Updates;
phone.leaveGroupCall#500377f9 call:InputGroupCall source:int = Updates;
phone.inviteToGroupCall#7b393160 call:InputGroupCall users:Vector<InputUser> = Updates;
phone.discardGroupCall#7a777135 call:InputGroupCall = Updates;
phone.toggleGroupCallSettings#74bbb43d flags:# reset_invite_hash:flags.1?true call:InputGroupCall join_muted:flags.0?Bool = Updates;
phone.toggleGroupCallRecord#f128c708 flags:# start:flags.0?true video:flags.2?true call:InputGroupCall title:flags.1?string video_portrait:flags.2?Bool = Updates;
phone.editGroupCallParticipant#a5273abf flags:# call:InputGroupCall participant:InputPeer muted:flags.0?Bool volume:flags.1?int raise_hand:flags.2?Bool video_stopped:flags.3?Bool video_paused:flags.4?Bool presentation_paused:flags.5?Bool = Updates;
phone.editGroupCallTitle#1ca6ac0a call:InputGroupCall title:string = Updates;
phone.toggleGroupCallStartSubscription#219c34e6 call:InputGroupCall subscribed:Bool = Updates;
phone.startScheduledGroupCall#5680e342 call:InputGroupCall = Updates;
phone.joinGroupCallPresentation#cbea6bc4 call:InputGroupCall params:DataJSON = Updates;
phone.leaveGroupCallPresentation#1c50d144 call:InputGroupCall = Updates;

account.getNotifyExceptions#53577479 flags:# compare_sound:flags.1?true compare_stories:flags.2?true peer:flags.0?InputNotifyPeer = Updates;

folders.editPeerFolders#6847d0ab folder_peers:Vector<InputFolderPeer> = Updates;

payments.assignAppStoreTransaction#80ed747d receipt:bytes purpose:InputStorePaymentPurpose = Updates;
payments.assignPlayMarketTransaction#dffd50d3 receipt:DataJSON purpose:InputStorePaymentPurpose = Updates;
payments.applyGiftCode#f6e26854 slug:string = Updates;
payments.launchPrepaidGiveaway#5ff58f20 peer:InputPeer giveaway_id:long purpose:InputStorePaymentPurpose = Updates;

chatlists.joinChatlistInvite#a6b1e39a slug:string peers:Vector<InputPeer> = Updates;
chatlists.joinChatlistUpdates#e089f8f5 chatlist:InputChatlist peers:Vector<InputPeer> = Updates;
chatlists.leaveChatlist#74fae13a chatlist:InputChatlist peers:Vector<InputPeer> = Updates;

stories.sendStory#e4e6694b flags:# pinned:flags.2?true noforwards:flags.4?true fwd_modified:flags.7?true peer:InputPeer media:InputMedia media_areas:flags.5?Vector<MediaArea> caption:flags.0?string entities:flags.1?Vector<MessageEntity> privacy_rules:Vector<InputPrivacyRule> random_id:long period:flags.3?int fwd_from_id:flags.6?InputPeer fwd_from_story:flags.6?int = Updates;
stories.editStory#b583ba46 flags:# peer:InputPeer id:int media:flags.0?InputMedia media_areas:flags.3?Vector<MediaArea> caption:flags.1?string entities:flags.1?Vector<MessageEntity> privacy_rules:flags.2?Vector<InputPrivacyRule> = Updates;
stories.activateStealthMode#57bbd166 flags:# past:flags.0?true future:flags.1?true = Updates;
stories.sendReaction#7fd736b2 flags:# add_to_recent:flags.0?true peer:InputPeer story_id:int reaction:Reaction = Updates;
stories.getAllReadPeerStories#9b5ae7f9 = Updates;

bots.allowSendMessage#f132e3ef bot:InputUser = Updates;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| updatesTooLong | Too many updates, it is necessary to execute updates.getDifference. |
| updateShortMessage | Info about a message sent to (received from) another user |
| updateShortChatMessage | Shortened constructor containing info on one new incoming text message from a chat |
| updateShort | Shortened constructor containing info on one update not requiring auxiliary data |
| updatesCombined | Constructor for a group of updates. |
| updates | Full constructor of updates |
| updateShortSentMessage | Shortened constructor containing info on one outgoing message to a contact (the destination chat has to be extracted from the method call that returned this object). |


## Methods
| Method | Description |
| ---- | ----------- |
| contacts.deleteContacts | Deletes several contacts from the list. |
| messages.sendMessage | Sends a message to a chat |
| messages.sendMedia | Send a media |
| messages.forwardMessages | Forwards messages by their IDs. |
| messages.editChatTitle | Changes chat name and sends a service message on it. |
| messages.editChatPhoto | Changes chat photo and sends a service message on it |
| messages.addChatUser | Adds a user to a chat and sends a service message on it.May also return 0-N updates of type updateGroupInvitePrivacyForbidden: it indicates we couldn't add a user to a chat because of their privacy settings; if required, an invite link can be shared with the user, instead. |
| messages.deleteChatUser | Deletes a user from a chat and sends a service message on it. |
| messages.createChat | Creates a new chat.May also return 0-N updates of type updateGroupInvitePrivacyForbidden: it indicates we couldn't add a user to a chat because of their privacy settings; if required, an invite link can be shared with the user, instead. |
| messages.importChatInvite | Import a chat invite and join a private chat/supergroup/channel |
| messages.startBot | Start a conversation with a bot using a deep linking parameter |
| channels.createChannel | Create a supergroup/channel. |
| channels.editAdmin | Modify the admin rights of a user in a supergroup/channel. |
| channels.editTitle | Edit the name of a channel/supergroup |
| channels.editPhoto | Change the photo of a channel/supergroup |
| channels.joinChannel | Join a channel/supergroup |
| channels.leaveChannel | Leave a channel/supergroup |
| channels.inviteToChannel | Invite users to a channel/supergroupMay also return 0-N updates of type updateGroupInvitePrivacyForbidden: it indicates we couldn't add a user to a chat because of their privacy settings; if required, an invite link can be shared with the user, instead. |
| channels.deleteChannel | Delete a channel/supergroup |
| messages.migrateChat | Turn a basic group into a supergroup |
| messages.sendInlineBotResult | Send a result obtained using messages.getInlineBotResults. |
| channels.toggleSignatures | Enable/disable message signatures in channels |
| messages.editMessage | Edit message |
| messages.getAllDrafts | Return all message drafts.  Returns all the latest updateDraftMessage updates related to all chats with drafts. |
| messages.setGameScore | Use this method to set the score of the specified user in a game sent as a normal message (bots only). |
| phone.discardCall | Refuse or end running call |
| phone.setCallRating | Rate a call, returns info about the rating message sent to the official VoIP bot. |
| channels.editBanned | Ban/unban/kick a user in a supergroup/channel. |
| messages.sendScreenshotNotification | Notify the other user in a private chat that a screenshot of the chat was taken |
| channels.deleteHistory | Delete the history of a supergroup |
| channels.togglePreHistoryHidden | Hide/unhide message history for new channel/supergroup users |
| messages.sendMultiMedia | Send an album or grouped media |
| messages.updatePinnedMessage | Pin a message |
| account.getNotifyExceptions | Returns list of chats with non-default notification settings |
| messages.sendVote | Vote in a pollStarting from layer 159, the vote will be sent from the peer specified using messages.saveDefaultSendAs. |
| messages.getPollResults | Get poll results |
| messages.editChatDefaultBannedRights | Edit the default banned rights of a channel/supergroup/group. |
| folders.editPeerFolders | Edit peers in peer folder |
| contacts.addContact | Add an existing telegram user as contact.Use contacts.importContacts to add contacts by phone number, without knowing their Telegram ID. |
| contacts.acceptContact | If the add contact action bar is active, add that user as contact |
| channels.editCreator | Transfer channel ownership |
| contacts.getLocated | Get users and geochats near you, see here » for more info. |
| channels.toggleSlowMode | Toggle supergroup slow mode: if enabled, users will only be able to send one message every seconds seconds |
| messages.sendScheduledMessages | Send scheduled messages right away |
| messages.deleteScheduledMessages | Delete scheduled messages |
| contacts.blockFromReplies | Stop getting notifications about discussion replies of a certain user in @replies |
| phone.createGroupCall | Create a group call or livestream |
| phone.joinGroupCall | Join a group call |
| phone.leaveGroupCall | Leave a group call |
| phone.inviteToGroupCall | Invite a set of users to a group call. |
| phone.discardGroupCall | Terminate a group call |
| phone.toggleGroupCallSettings | Change group call settings |
| messages.setHistoryTTL | Set maximum Time-To-Live of all messages in the specified chat |
| channels.convertToGigagroup | Convert a supergroup to a gigagroup, when requested by channel suggestions. |
| phone.toggleGroupCallRecord | Start or stop recording a group call: the recorded audio and video streams will be automatically sent to Saved messages (the chat with ourselves). |
| phone.editGroupCallParticipant | Edit information about a given group call participantNote: flags.N?Bool parameters can have three possible values:- If the TL flag is not set, the previous value will not be changed.- If the TL flag is set and contains a boolTrue, the previous value will be overwritten to true.- If the TL flag is set and contains a boolFalse, the previous value will be overwritten to false. |
| phone.editGroupCallTitle | Edit the title of a group call or livestream |
| phone.toggleGroupCallStartSubscription | Subscribe or unsubscribe to a scheduled group call |
| phone.startScheduledGroupCall | Start a scheduled group call. |
| phone.joinGroupCallPresentation | Start screen sharing in a call |
| phone.leaveGroupCallPresentation | Stop screen sharing in a group call |
| messages.setChatTheme | Change the chat theme of a certain chat |
| messages.hideChatJoinRequest | Dismiss or approve a chat join request related to a specific chat or channel. |
| messages.hideAllChatJoinRequests | Dismiss or approve all join requests related to a specific chat or channel. |
| messages.toggleNoForwards | Enable or disable content protection on a channel or chat |
| messages.sendReaction | React to message.Starting from layer 159, the reaction will be sent from the peer specified using messages.saveDefaultSendAs. |
| messages.getMessagesReactions | Get message reactions » |
| messages.setChatAvailableReactions | Change the set of message reactions » that can be used in a certain group, supergroup or channel |
| messages.sendWebViewData | Used by the user to relay data from an opened reply keyboard bot mini app to the bot that owns it. |
| channels.toggleJoinToSend | Set whether all users should join a discussion group in order to comment on a post » |
| channels.toggleJoinRequest | Set whether all users should request admin approval to join the group ». |
| payments.assignAppStoreTransaction | Informs server about a purchase made through the App Store: for official applications only. |
| payments.assignPlayMarketTransaction | Informs server about a purchase made through the Play Store: for official applications only. |
| messages.getExtendedMedia | Get information about extended media |
| channels.toggleForum | Enable or disable forum functionality in a supergroup. |
| channels.createForumTopic | Create a forum topic; requires manage_topics rights. |
| channels.editForumTopic | Edit forum topic; requires manage_topics rights. |
| channels.updatePinnedForumTopic | Pin or unpin forum topics |
| channels.reorderPinnedForumTopics | Reorder pinned forum topics |
| channels.toggleAntiSpam | Enable or disable the native antispam system. |
| channels.toggleParticipantsHidden | Hide or display the participants list in a supergroup.The supergroup must have at least hidden_members_group_size_min participants in order to use this method, as specified by the client configuration parameters ». |
| messages.sendBotRequestedPeer | Send one or more chosen peers, as requested by a keyboardButtonRequestPeer button. |
| chatlists.joinChatlistInvite | Import a chat folder deep link », joining some or all the chats in the folder. |
| chatlists.joinChatlistUpdates | Join channels and supergroups recently added to a chat folder deep link ». |
| chatlists.leaveChatlist | Delete a folder imported using a chat folder deep link » |
| messages.setChatWallPaper | Set a custom wallpaper » in a specific private chat with another user. |
| stories.sendStory | Uploads a Telegram Story. |
| stories.editStory | Edit an uploaded story |
| stories.activateStealthMode | Activates stories stealth mode, see here » for more info.Will return an updateStoriesStealthMode. |
| stories.sendReaction | React to a story. |
| bots.allowSendMessage | Allow the specified bot to send us messages |
| stories.getAllReadPeerStories | Obtain the latest read story ID for all peers when first logging in, returned as a list of updateReadStories updates, see here » for more info. |
| payments.applyGiftCode | Apply a Telegram Premium giftcode » |
| payments.launchPrepaidGiveaway | Launch a prepaid giveaway ». |
| channels.updateColor | Update the accent color and background custom emoji » of a channel. |
| channels.toggleViewForumAsMessages | Users may also choose to display messages from all topics of a forum as if they were sent to a normal group, using a "View as messages" setting in the local client: this setting only affects the current account, and is synced to other logged in sessions using this method.Invoking this method will update the value of the view_forum_as_messages flag of channelFull or dialog and emit an updateChannelViewForumAsMessages. |
| channels.updateEmojiStatus | Set an emoji status for a channel. |


