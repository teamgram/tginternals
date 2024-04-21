# Bool
Boolean type.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;

---functions---

auth.resetAuthorizations#9fab0d1a = Bool;
auth.bindTempAuthKey#cdd42a05 perm_auth_key_id:long nonce:long expires_at:int encrypted_message:bytes = Bool;
auth.cancelCode#1f040578 phone_number:string phone_code_hash:string = Bool;
auth.dropTempAuthKeys#8e48a188 except_auth_keys:Vector<long> = Bool;
auth.checkRecoveryPassword#d36bf79 code:string = Bool;
auth.requestFirebaseSms#89464b50 flags:# phone_number:string phone_code_hash:string safety_net_token:flags.0?string ios_push_secret:flags.1?string = Bool;

account.registerDevice#ec86017a flags:# no_muted:flags.0?true token_type:int token:string app_sandbox:Bool secret:bytes other_uids:Vector<long> = Bool;
account.unregisterDevice#6a0d3206 token_type:int token:string other_uids:Vector<long> = Bool;
account.updateNotifySettings#84be5b93 peer:InputNotifyPeer settings:InputPeerNotifySettings = Bool;
account.resetNotifySettings#db7e1747 = Bool;
account.updateStatus#6628562c offline:Bool = Bool;
account.reportPeer#c5ba3d86 peer:InputPeer reason:ReportReason message:string = Bool;
account.checkUsername#2714d86c username:string = Bool;
account.deleteAccount#a2c0cf74 flags:# reason:string password:flags.0?InputCheckPasswordSRP = Bool;
account.setAccountTTL#2442485e ttl:AccountDaysTTL = Bool;
account.updateDeviceLocked#38df3532 period:int = Bool;
account.resetAuthorization#df77f3bc hash:long = Bool;
account.updatePasswordSettings#a59b102f password:InputCheckPasswordSRP new_settings:account.PasswordInputSettings = Bool;
account.confirmPhone#5f2178c3 phone_code_hash:string phone_code:string = Bool;
account.resetWebAuthorization#2d01b9ef hash:long = Bool;
account.resetWebAuthorizations#682d2594 = Bool;
account.deleteSecureValue#b880bc4b types:Vector<SecureValueType> = Bool;
account.acceptAuthorization#f3ed4c73 bot_id:long scope:string public_key:string value_hashes:Vector<SecureValueHash> credentials:SecureCredentialsEncrypted = Bool;
account.verifyPhone#4dd3a7f6 phone_number:string phone_code_hash:string phone_code:string = Bool;
account.finishTakeoutSession#1d2652ee flags:# success:flags.0?true = Bool;
account.confirmPasswordEmail#8fdf1920 code:string = Bool;
account.resendPasswordEmail#7a7f2a15 = Bool;
account.cancelPasswordEmail#c1cbd5b6 = Bool;
account.getContactSignUpNotification#9f07c728 = Bool;
account.setContactSignUpNotification#cff43f61 silent:Bool = Bool;
account.saveWallPaper#6c5a5b37 wallpaper:InputWallPaper unsave:Bool settings:WallPaperSettings = Bool;
account.installWallPaper#feed5769 wallpaper:InputWallPaper settings:WallPaperSettings = Bool;
account.resetWallPapers#bb3b9804 = Bool;
account.saveAutoDownloadSettings#76f36233 flags:# low:flags.0?true high:flags.1?true settings:AutoDownloadSettings = Bool;
account.saveTheme#f257106c theme:InputTheme unsave:Bool = Bool;
account.installTheme#c727bb3b flags:# dark:flags.0?true theme:flags.1?InputTheme format:flags.2?string base_theme:flags.3?BaseTheme = Bool;
account.setContentSettings#b574b16b flags:# sensitive_enabled:flags.0?true = Bool;
account.reportProfilePhoto#fa8cc6f5 peer:InputPeer photo_id:InputPhoto reason:ReportReason message:string = Bool;
account.declinePasswordReset#4c9409f6 = Bool;
account.setAuthorizationTTL#bf899aa0 authorization_ttl_days:int = Bool;
account.changeAuthorizationSettings#40f48462 flags:# confirmed:flags.3?true hash:long encrypted_requests_disabled:flags.0?Bool call_requests_disabled:flags.1?Bool = Bool;
account.updateEmojiStatus#fbd3de6b emoji_status:EmojiStatus = Bool;
account.clearRecentEmojiStatuses#18201aae = Bool;
account.reorderUsernames#ef500eab order:Vector<string> = Bool;
account.toggleUsername#58d6b376 username:string active:Bool = Bool;
account.saveAutoSaveSettings#d69b8361 flags:# users:flags.0?true chats:flags.1?true broadcasts:flags.2?true peer:flags.3?InputPeer settings:AutoSaveSettings = Bool;
account.deleteAutoSaveExceptions#53bc0020 = Bool;
account.invalidateSignInCodes#ca8ae8ba codes:Vector<string> = Bool;
account.updateColor#7cefa15d flags:# for_profile:flags.1?true color:flags.2?int background_emoji_id:flags.0?long = Bool;

contacts.deleteByPhones#1013fd9e phones:Vector<string> = Bool;
contacts.block#2e2e8734 flags:# my_stories_from:flags.0?true id:InputPeer = Bool;
contacts.unblock#b550d328 flags:# my_stories_from:flags.0?true id:InputPeer = Bool;
contacts.resetTopPeerRating#1ae373ac category:TopPeerCategory peer:InputPeer = Bool;
contacts.resetSaved#879537f1 = Bool;
contacts.toggleTopPeers#8514bdda enabled:Bool = Bool;
contacts.editCloseFriends#ba6705f0 id:Vector<long> = Bool;
contacts.setBlocked#94c65c76 flags:# my_stories_from:flags.0?true id:Vector<InputPeer> limit:int = Bool;

messages.setTyping#58943ee2 flags:# peer:InputPeer top_msg_id:flags.0?int action:SendMessageAction = Bool;
messages.reportSpam#cf1592db peer:InputPeer = Bool;
messages.report#8953ab4e peer:InputPeer id:Vector<int> reason:ReportReason message:string = Bool;
messages.discardEncryption#f393aea0 flags:# delete_history:flags.0?true chat_id:int = Bool;
messages.setEncryptedTyping#791451ed peer:InputEncryptedChat typing:Bool = Bool;
messages.readEncryptedHistory#7f4b690a peer:InputEncryptedChat max_date:int = Bool;
messages.reportEncryptedSpam#4b0c8c0f peer:InputEncryptedChat = Bool;
messages.uninstallStickerSet#f96e55de stickerset:InputStickerSet = Bool;
messages.editChatAdmin#a85bd1c2 chat_id:long user_id:InputUser is_admin:Bool = Bool;
messages.reorderStickerSets#78337739 flags:# masks:flags.0?true emojis:flags.1?true order:Vector<long> = Bool;
messages.saveGif#327a30cb id:InputDocument unsave:Bool = Bool;
messages.setInlineBotResults#bb12a419 flags:# gallery:flags.0?true private:flags.1?true query_id:long results:Vector<InputBotInlineResult> cache_time:int next_offset:flags.2?string switch_pm:flags.3?InlineBotSwitchPM switch_webview:flags.4?InlineBotWebView = Bool;
messages.editInlineBotMessage#83557dba flags:# no_webpage:flags.1?true invert_media:flags.16?true id:InputBotInlineMessageID message:flags.11?string media:flags.14?InputMedia reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> = Bool;
messages.setBotCallbackAnswer#d58f130a flags:# alert:flags.1?true query_id:long message:flags.0?string url:flags.2?string cache_time:int = Bool;
messages.saveDraft#7ff3b806 flags:# no_webpage:flags.1?true invert_media:flags.6?true reply_to:flags.4?InputReplyTo peer:InputPeer message:string entities:flags.3?Vector<MessageEntity> media:flags.5?InputMedia = Bool;
messages.readFeaturedStickers#5b118126 id:Vector<long> = Bool;
messages.saveRecentSticker#392718f8 flags:# attached:flags.0?true id:InputDocument unsave:Bool = Bool;
messages.clearRecentStickers#8999602d flags:# attached:flags.0?true = Bool;
messages.setInlineGameScore#15ad9f64 flags:# edit_message:flags.0?true force:flags.1?true id:InputBotInlineMessageID user_id:InputUser score:int = Bool;
messages.toggleDialogPin#a731e257 flags:# pinned:flags.0?true peer:InputDialogPeer = Bool;
messages.reorderPinnedDialogs#3b1adf37 flags:# force:flags.0?true folder_id:int order:Vector<InputDialogPeer> = Bool;
messages.setBotShippingResults#e5f672fa flags:# query_id:long error:flags.0?string shipping_options:flags.1?Vector<ShippingOption> = Bool;
messages.setBotPrecheckoutResults#9c2dd95 flags:# success:flags.1?true query_id:long error:flags.0?string = Bool;
messages.faveSticker#b9ffc55b id:InputDocument unfave:Bool = Bool;
messages.markDialogUnread#c286d98f flags:# unread:flags.0?true peer:InputDialogPeer = Bool;
messages.clearAllDrafts#7e58ee9c = Bool;
messages.editChatAbout#def60797 peer:InputPeer about:string = Bool;
messages.hidePeerSettingsBar#4facb138 peer:InputPeer = Bool;
messages.toggleStickerSets#b5052fea flags:# uninstall:flags.0?true archive:flags.1?true unarchive:flags.2?true stickersets:Vector<InputStickerSet> = Bool;
messages.updateDialogFilter#1ad4a04a flags:# id:int filter:flags.0?DialogFilter = Bool;
messages.updateDialogFiltersOrder#c563c1e4 order:Vector<int> = Bool;
messages.readDiscussion#f731a9f4 peer:InputPeer msg_id:int read_max_id:int = Bool;
messages.deleteChat#5bd0ee50 chat_id:long = Bool;
messages.startHistoryImport#b43df344 peer:InputPeer import_id:long = Bool;
messages.deleteRevokedExportedChatInvites#56987bd5 peer:InputPeer admin_id:InputUser = Bool;
messages.deleteExportedChatInvite#d464a42b peer:InputPeer link:string = Bool;
messages.saveDefaultSendAs#ccfddf96 peer:InputPeer send_as:InputPeer = Bool;
messages.setDefaultReaction#4f47a016 reaction:Reaction = Bool;
messages.toggleBotInAttachMenu#69f59d69 flags:# write_allowed:flags.0?true bot:InputUser enabled:Bool = Bool;
messages.prolongWebView#b0d81a83 flags:# silent:flags.5?true peer:InputPeer bot:InputUser query_id:long reply_to:flags.0?InputReplyTo send_as:flags.13?InputPeer = Bool;
messages.rateTranscribedAudio#7f1d072f peer:InputPeer msg_id:int transcription_id:long good:Bool = Bool;
messages.reportReaction#3f64c076 peer:InputPeer id:int reaction_peer:InputPeer = Bool;
messages.clearRecentReactions#9dfeefb4 = Bool;
messages.setDefaultHistoryTTL#9eb51445 period:int = Bool;
messages.togglePeerTranslations#e47cb579 flags:# disabled:flags.0?true peer:InputPeer = Bool;
messages.toggleSavedDialogPin#ac81bbde flags:# pinned:flags.0?true peer:InputDialogPeer = Bool;
messages.reorderPinnedSavedDialogs#8b716587 flags:# force:flags.0?true order:Vector<InputDialogPeer> = Bool;

upload.saveFilePart#b304a621 file_id:long file_part:int bytes:bytes = Bool;
upload.saveBigFilePart#de7b673d file_id:long file_part:int file_total_parts:int bytes:bytes = Bool;

channels.readHistory#cc104937 channel:InputChannel max_id:int = Bool;
channels.reportSpam#f44a8315 channel:InputChannel participant:InputPeer id:Vector<int> = Bool;
channels.checkUsername#10e6bd2c channel:InputChannel username:string = Bool;
channels.updateUsername#3514b3de channel:InputChannel username:string = Bool;
channels.setStickers#ea8ca4f9 channel:InputChannel stickerset:InputStickerSet = Bool;
channels.readMessageContents#eab5dc38 channel:InputChannel id:Vector<int> = Bool;
channels.setDiscussionGroup#40582bb2 broadcast:InputChannel group:InputChannel = Bool;
channels.editLocation#58e63f6d channel:InputChannel geo_point:InputGeoPoint address:string = Bool;
channels.viewSponsoredMessage#beaedb94 channel:InputChannel random_id:bytes = Bool;
channels.reorderUsernames#b45ced1d channel:InputChannel order:Vector<string> = Bool;
channels.toggleUsername#50f24105 channel:InputChannel username:string active:Bool = Bool;
channels.deactivateAllUsernames#a245dd3 channel:InputChannel = Bool;
channels.reportAntiSpamFalsePositive#a850a693 channel:InputChannel msg_id:int = Bool;
channels.clickSponsoredMessage#18afbc93 channel:InputChannel random_id:bytes = Bool;

help.setBotUpdatesStatus#ec22cfcd pending_updates_count:int message:string = Bool;
help.acceptTermsOfService#ee72f79a id:DataJSON = Bool;
help.saveAppLog#6f02f748 events:Vector<InputAppEvent> = Bool;
help.hidePromoData#1e251c95 peer:InputPeer = Bool;
help.dismissSuggestion#f50dbaa1 peer:InputPeer suggestion:string = Bool;

bots.answerWebhookJSONQuery#e6213f4d query_id:long data:DataJSON = Bool;
bots.setBotCommands#517165a scope:BotCommandScope lang_code:string commands:Vector<BotCommand> = Bool;
bots.resetBotCommands#3d8de0f9 scope:BotCommandScope lang_code:string = Bool;
bots.setBotMenuButton#4504d54f user_id:InputUser button:BotMenuButton = Bool;
bots.setBotBroadcastDefaultAdminRights#788464e1 admin_rights:ChatAdminRights = Bool;
bots.setBotGroupDefaultAdminRights#925ec9ea admin_rights:ChatAdminRights = Bool;
bots.setBotInfo#10cf3123 flags:# bot:flags.2?InputUser lang_code:string name:flags.3?string about:flags.0?string description:flags.1?string = Bool;
bots.reorderUsernames#9709b1c2 bot:InputUser order:Vector<string> = Bool;
bots.toggleUsername#53ca973 bot:InputUser username:string active:Bool = Bool;
bots.canSendMessage#1359f4e6 bot:InputUser = Bool;

payments.clearSavedInfo#d83d70c1 flags:# credentials:flags.0?true info:flags.1?true = Bool;
payments.canPurchasePremium#9fc19eb6 purpose:InputStorePaymentPurpose = Bool;

phone.receivedCall#17d54f61 peer:InputPhoneCall = Bool;
phone.saveCallDebug#277add7e peer:InputPhoneCall debug:DataJSON = Bool;
phone.sendSignalingData#ff7a9383 peer:InputPhoneCall data:bytes = Bool;
phone.saveDefaultGroupCallJoinAs#575e1f8c peer:InputPeer join_as:InputPeer = Bool;
phone.saveCallLog#41248786 peer:InputPhoneCall file:InputFile = Bool;

users.setSecureValueErrors#90c894b5 id:InputUser errors:Vector<SecureValueError> = Bool;

stickers.checkShortName#284b3639 short_name:string = Bool;
stickers.deleteStickerSet#87704394 stickerset:InputStickerSet = Bool;

chatlists.deleteExportedInvite#719c5c5e chatlist:InputChatlist slug:string = Bool;
chatlists.hideChatlistUpdates#66e486fb chatlist:InputChatlist = Bool;

stories.canSendStory#c7dfdfdd peer:InputPeer = Bool;
stories.toggleAllStoriesHidden#7c2557c4 hidden:Bool = Bool;
stories.incrementStoryViews#b2028afb peer:InputPeer id:Vector<int> = Bool;
stories.report#1923fa8c peer:InputPeer id:Vector<int> reason:ReportReason message:string = Bool;
stories.togglePeerStoriesHidden#bd0415c4 peer:InputPeer hidden:Bool = Bool;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| boolFalse | Constructor may be interpreted as a booleanfalse value. |
| boolTrue | The constructor can be interpreted as a booleantrue value. |


## Methods
| Method | Description |
| ---- | ----------- |
| auth.resetAuthorizations | Terminates all user's authorized sessions except for the current one.After calling this method it is necessary to reregister the current device using the method account.registerDevice |
| auth.bindTempAuthKey | Binds a temporary authorization key temp_auth_key_id to the permanent authorization key perm_auth_key_id. Each permanent key may only be bound to one temporary key at a time, binding a new temporary key overwrites the previous one.For more information, see Perfect Forward Secrecy. |
| account.registerDevice | Register device to receive PUSH notifications |
| account.unregisterDevice | Deletes a device by its token, stops sending PUSH-notifications to it. |
| account.updateNotifySettings | Edits notification settings from a given user/group, from all users/all groups. |
| account.resetNotifySettings | Resets all notification settings from users and groups. |
| account.updateStatus | Updates online user status. |
| account.reportPeer | Report a peer for violation of telegram's Terms of Service |
| contacts.deleteByPhones | Delete contacts by phone number |
| contacts.block | Adds a peer to a blocklist, see here » for more info. |
| contacts.unblock | Deletes a peer from a blocklist, see here » for more info. |
| messages.setTyping | Sends a current user typing event (see SendMessageAction for all event types) to a conversation partner or group. |
| messages.reportSpam | Report a new incoming chat for spam, if the peer settings of the chat allow us to do that |
| messages.report | Report a message in a chat for violation of telegram's Terms of Service |
| upload.saveFilePart | Saves a part of file for further sending to one of the methods. |
| messages.discardEncryption | Cancels a request for creation and/or delete info on secret chat. |
| messages.setEncryptedTyping | Send typing event by the current user to a secret chat. |
| messages.readEncryptedHistory | Marks message history within a secret chat as read. |
| messages.reportEncryptedSpam | Report a secret chat for spam |
| upload.saveBigFilePart | Saves a part of a large file (over 10 MB in size) to be later passed to one of the methods. |
| account.checkUsername | Validates a username and checks availability. |
| account.deleteAccount | Delete the user's account from the telegram servers.Can also be used to delete the account of a user that provided the login code, but forgot the 2FA password and no recovery method is configured, see here » for more info on password recovery, and here » for more info on account deletion. |
| account.setAccountTTL | Set account self-destruction period |
| account.updateDeviceLocked | When client-side passcode lock feature is enabled, will not show message texts in incoming PUSH notifications. |
| account.resetAuthorization | Log out an active authorized session by its hash |
| account.updatePasswordSettings | Set a new 2FA password |
| messages.uninstallStickerSet | Uninstall a stickerset |
| channels.readHistory | Mark channel/supergroup history as read |
| channels.reportSpam | Reports some messages from a user in a supergroup as spam; requires administrator rights in the supergroup |
| channels.checkUsername | Check if a username is free and can be assigned to a channel/supergroup |
| channels.updateUsername | Change or remove the username of a supergroup/channel |
| messages.editChatAdmin | Make a user admin in a basic group. |
| messages.reorderStickerSets | Reorder installed stickersets |
| messages.saveGif | Add GIF to saved gifs list |
| messages.setInlineBotResults | Answer an inline query, for bots only |
| auth.cancelCode | Cancel the login verification code |
| messages.editInlineBotMessage | Edit an inline bot message |
| messages.setBotCallbackAnswer | Set the callback answer to a user button press (bots only) |
| contacts.resetTopPeerRating | Reset rating of top peer |
| messages.saveDraft | Save a message draft associated to a chat. |
| messages.readFeaturedStickers | Mark new featured stickers as read |
| messages.saveRecentSticker | Add/remove sticker from recent stickers list |
| messages.clearRecentStickers | Clear recent stickers |
| account.confirmPhone | Confirm a phone number to cancel account deletion, for more info click here » |
| auth.dropTempAuthKeys | Delete all temporary authorization keys except for the ones specified |
| messages.setInlineGameScore | Use this method to set the score of the specified user in a game sent as an inline message (bots only). |
| help.setBotUpdatesStatus | Informs the server about the number of pending bot updates if they haven't been processed for a long time; for bots only |
| messages.toggleDialogPin | Pin/unpin a dialog |
| messages.reorderPinnedDialogs | Reorder pinned dialogs |
| bots.answerWebhookJSONQuery | Answers a custom query; for bots only |
| payments.clearSavedInfo | Clear saved payment information |
| messages.setBotShippingResults | If you sent an invoice requesting a shipping address and the parameter is_flexible was specified, the bot will receive an updateBotShippingQuery update. Use this method to reply to shipping queries. |
| messages.setBotPrecheckoutResults | Once the user has confirmed their payment and shipping details, the bot receives an updateBotPrecheckoutQuery update.  Use this method to respond to such pre-checkout queries.  Note: Telegram must receive an answer within 10 seconds after the pre-checkout query was sent. |
| phone.receivedCall | Optional: notify the server that the user is currently busy in a call: this will automatically refuse all incoming phone calls until the current phone call is ended. |
| phone.saveCallDebug | Send phone call debug data to server |
| channels.setStickers | Associate a stickerset to the supergroup |
| messages.faveSticker | Mark or unmark a sticker as favorite |
| channels.readMessageContents | Mark channel/supergroup message contents as read |
| contacts.resetSaved | Removes all contacts without an associated Telegram account. |
| account.resetWebAuthorization | Log out an active web telegram login session |
| account.resetWebAuthorizations | Reset all active web telegram login sessions |
| help.acceptTermsOfService | Accept the new terms of service |
| account.deleteSecureValue | Delete stored Telegram Passport documents, for more info see the passport docs » |
| users.setSecureValueErrors | Notify the user that the sent passport data contains some errors The user will not be able to re-submit their Passport data to you until the errors are fixed (the contents of the field for which you returned the error must change).Use this if the data submitted by the user doesn't satisfy the standards your service requires for any reason. For example, if a birthday date seems invalid, a submitted document is blurry, a scan shows evidence of tampering, etc. Supply some details in the error message to make sure the user knows how to correct the issues. |
| account.acceptAuthorization | Sends a Telegram Passport authorization form, effectively sharing data with the service |
| account.verifyPhone | Verify a phone number for telegram passport. |
| account.finishTakeoutSession | Terminate a takeout session, see here » for more info. |
| messages.markDialogUnread | Manually mark dialog as unread |
| contacts.toggleTopPeers | Enable/disable top peers |
| messages.clearAllDrafts | Clear all drafts. |
| help.saveAppLog | Saves logs of application on the server. |
| account.confirmPasswordEmail | Verify an email to use as 2FA recovery method. |
| account.resendPasswordEmail | Resend the code to verify an email to use as 2FA recovery method. |
| account.cancelPasswordEmail | Cancel the code that was sent to verify an email to use as 2FA recovery method. |
| account.getContactSignUpNotification | Whether the user will receive notifications when contacts sign up |
| account.setContactSignUpNotification | Toggle contact sign up notifications |
| messages.editChatAbout | Edit the description of a group/supergroup/channel. |
| account.saveWallPaper | Install/uninstall wallpaper |
| account.installWallPaper | Install wallpaper |
| account.resetWallPapers | Delete all installed wallpapers, reverting to the default wallpaper set. |
| account.saveAutoDownloadSettings | Change media autodownload settings |
| channels.setDiscussionGroup | Associate a group to a channel as discussion group for that channel |
| messages.hidePeerSettingsBar | Should be called after the user hides the report spam/add as contact bar of a new chat, effectively prevents the user from executing the actions specified in the action bar ». |
| channels.editLocation | Edit location of geogroup, see here » for more info on geogroups. |
| account.saveTheme | Save a theme |
| account.installTheme | Install a theme |
| account.setContentSettings | Set sensitive content settings (for viewing or hiding NSFW content) |
| messages.toggleStickerSets | Apply changes to multiple stickersets |
| messages.updateDialogFilter | Update folder |
| messages.updateDialogFiltersOrder | Reorder folders |
| bots.setBotCommands | Set bot command list |
| help.hidePromoData | Hide MTProxy/Public Service Announcement information |
| phone.sendSignalingData | Send VoIP signaling data |
| help.dismissSuggestion | Dismiss a suggestion, see here for more info ». |
| messages.readDiscussion | Mark a thread as read |
| messages.deleteChat | Delete a chat |
| messages.startHistoryImport | Complete the history import process, importing all messages into the chat.  To be called only after initializing the import with messages.initHistoryImport and uploading all files using messages.uploadImportedMedia. |
| messages.deleteRevokedExportedChatInvites | Delete all revoked chat invites |
| messages.deleteExportedChatInvite | Delete a chat invite |
| account.reportProfilePhoto | Report a profile photo of a dialog |
| phone.saveDefaultGroupCallJoinAs | Set the default peer that will be used to join a group call in a specific dialog. |
| stickers.checkShortName | Check whether the given short name is available |
| bots.resetBotCommands | Clear bot commands for the specified bot scope and language code |
| account.declinePasswordReset | Abort a pending 2FA password reset, see here for more info » |
| auth.checkRecoveryPassword | Check if the 2FA recovery code sent using auth.requestPasswordRecovery is valid, before passing it to auth.recoverPassword. |
| channels.viewSponsoredMessage | Mark a specific sponsored message as read |
| messages.saveDefaultSendAs | Change the default peer that should be used when sending messages, reactions, poll votes to a specific group |
| account.setAuthorizationTTL | Set time-to-live of current session |
| account.changeAuthorizationSettings | Change settings related to a session. |
| messages.setDefaultReaction | Change default emoji reaction to use in the quick reaction menu: the value is synced across devices and can be fetched using help.getConfig, reactions_default field. |
| messages.toggleBotInAttachMenu | Enable or disable web bot attachment menu » |
| messages.prolongWebView | Indicate to the server (from the user side) that the user is still using a web app.If the method returns a QUERY_ID_INVALID error, the webview must be closed. |
| bots.setBotMenuButton | Sets the menu button action » for a given user or for all users |
| bots.setBotBroadcastDefaultAdminRights | Set the default suggested admin rights for bots being added as admins to channels, see here for more info on how to handle them ». |
| bots.setBotGroupDefaultAdminRights | Set the default suggested admin rights for bots being added as admins to groups, see here for more info on how to handle them ». |
| phone.saveCallLog | Save phone call debug information |
| messages.rateTranscribedAudio | Rate transcribed voice message |
| payments.canPurchasePremium | Checks whether Telegram Premium purchase is possible. Must be called before in-store Premium purchase, official apps only. |
| account.updateEmojiStatus | Set an emoji status |
| account.clearRecentEmojiStatuses | Clears list of recently used emoji statuses |
| messages.reportReaction | Report a message reaction |
| messages.clearRecentReactions | Clear recently used message reactions |
| account.reorderUsernames | Reorder usernames associated with the currently logged-in user. |
| account.toggleUsername | Activate or deactivate a purchased fragment.com username associated to the currently logged-in user. |
| channels.reorderUsernames | Reorder active usernames |
| channels.toggleUsername | Activate or deactivate a purchased fragment.com username associated to a supergroup or channel we own. |
| channels.deactivateAllUsernames | Disable all purchased usernames of a supergroup or channel |
| channels.reportAntiSpamFalsePositive | Report a native antispam false positive |
| messages.setDefaultHistoryTTL | Changes the default value of the Time-To-Live setting, applied to all new chats. |
| auth.requestFirebaseSms | Request an SMS code via Firebase. |
| messages.togglePeerTranslations | Show or hide the real-time chat translation popup for a certain chat |
| account.saveAutoSaveSettings | Modify autosave settings |
| account.deleteAutoSaveExceptions | Clear all peer-specific autosave settings. |
| stickers.deleteStickerSet | Deletes a stickerset we created, bots only. |
| bots.setBotInfo | Set localized name, about text and description of a bot (or of the current account, if called by a bot). |
| chatlists.deleteExportedInvite | Delete a previously created chat folder deep link ». |
| chatlists.hideChatlistUpdates | Dismiss new pending peers recently added to a chat folder deep link ». |
| bots.reorderUsernames | Reorder usernames associated to a bot we own. |
| bots.toggleUsername | Activate or deactivate a purchased fragment.com username associated to a bot we own. |
| account.invalidateSignInCodes | Invalidate the specified login codes, see here » for more info. |
| channels.clickSponsoredMessage | Informs the server that the user has either:- Clicked on a link in the sponsored message- Has opened a sponsored chat or a sponsored website via the associated button- Has opened the sponsored chat via the sponsored message name, the sponsored message photo, or a mention in the sponsored message |
| contacts.editCloseFriends | Edit the close friends list, see here » for more info. |
| stories.canSendStory | Check whether we can post stories as the specified peer. |
| stories.toggleAllStoriesHidden | Hide the active stories of a specific peer, preventing them from being displayed on the action bar on the homescreen. |
| stories.incrementStoryViews | Increment the view counter of one or more stories. |
| stories.report | Report a story. |
| contacts.setBlocked | Replace the contents of an entire blocklist, see here for more info ». |
| bots.canSendMessage | Check whether the specified bot can send us messages |
| stories.togglePeerStoriesHidden | Hide the active stories of a user, preventing them from being displayed on the action bar on the homescreen, see here » for more info. |
| account.updateColor | Update the accent color and background custom emoji » of the current account. |
| messages.toggleSavedDialogPin | Pin or unpin a saved message dialog ». |
| messages.reorderPinnedSavedDialogs | Reorder pinned saved message dialogs ». |


