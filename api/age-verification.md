# Age verification

Some legislations require age verification to view restricted content: Telegram implements this through the Main Mini App of a special bot.

```
restrictionReason#d072acb4 platform:string reason:string text:string = RestrictionReason;

user#20b1422 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true contact_require_premium:flags2.10?true bot_business:flags2.11?true bot_has_main_app:flags2.13?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor bot_active_users:flags2.12?int bot_verification_icon:flags2.14?long send_paid_messages_stars:flags2.15?long = User;

channel#fe685355 flags:# creator:flags.0?true left:flags.2?true broadcast:flags.5?true verified:flags.7?true megagroup:flags.8?true restricted:flags.9?true signatures:flags.11?true min:flags.12?true scam:flags.19?true has_link:flags.20?true has_geo:flags.21?true slowmode_enabled:flags.22?true call_active:flags.23?true call_not_empty:flags.24?true fake:flags.25?true gigagroup:flags.26?true noforwards:flags.27?true join_to_send:flags.28?true join_request:flags.29?true forum:flags.30?true flags2:# stories_hidden:flags2.1?true stories_hidden_min:flags2.2?true stories_unavailable:flags2.3?true signature_profiles:flags2.12?true autotranslation:flags2.15?true broadcast_messages_allowed:flags2.16?true monoforum:flags2.17?true forum_tabs:flags2.19?true id:long access_hash:flags.13?long title:string username:flags.6?string photo:ChatPhoto date:int restriction_reason:flags.9?Vector<RestrictionReason> admin_rights:flags.14?ChatAdminRights banned_rights:flags.15?ChatBannedRights default_banned_rights:flags.18?ChatBannedRights participants_count:flags.17?int usernames:flags2.0?Vector<Username> stories_max_id:flags2.4?int color:flags2.7?PeerColor profile_color:flags2.8?PeerColor emoji_status:flags2.9?EmojiStatus level:flags2.10?int subscription_until_date:flags2.11?int bot_verification_icon:flags2.13?long send_paid_messages_stars:flags2.14?long linked_monoforum_id:flags2.18?long = Chat;

message#9815cec8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true from_scheduled:flags.18?true legacy:flags.19?true edit_hide:flags.21?true pinned:flags.24?true noforwards:flags.26?true invert_media:flags.27?true flags2:# offline:flags2.1?true video_processing_pending:flags2.4?true paid_suggested_post_stars:flags2.8?true paid_suggested_post_ton:flags2.9?true id:int from_id:flags.8?Peer from_boosts_applied:flags.29?int peer_id:Peer saved_peer_id:flags.28?Peer fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long via_business_bot_id:flags2.0?long reply_to:flags.3?MessageReplyHeader date:int message:string media:flags.9?MessageMedia reply_markup:flags.6?ReplyMarkup entities:flags.7?Vector<MessageEntity> views:flags.10?int forwards:flags.10?int replies:flags.23?MessageReplies edit_date:flags.15?int post_author:flags.16?string grouped_id:flags.17?long reactions:flags.20?MessageReactions restriction_reason:flags.22?Vector<RestrictionReason> ttl_period:flags.25?int quick_reply_shortcut_id:flags.30?int effect:flags2.2?long factcheck:flags2.3?FactCheck report_delivery_until_date:flags2.5?int paid_message_stars:flags2.6?long suggested_post:flags2.7?SuggestedPost = Message;
```

Access to users, chats, channels and individual messages may be restricted for a variety of platforms and reasons through the restriction_reason field.

To check if any of the restriction reasons applies to us, iterate over the restrictionReason objects in the restriction_reason field, keeping only reasons where:

- restrictionReason.platform is equal to all

- For all platforms specified in restrictionReason.platform (which contains a concatenated list of one or more multiple platforms, separated by -):

- At least one matches the current platform (hardcoded within the client based on the current platform, i.e. ios, android, wp, etc)

- At least one matches any of the platforms specified in the restriction_add_platforms dynamic configuration parameter »

- restrictionReason.reason is not contained in the list of reasons specified in the ignore_restriction_reasons dynamic configuration parameter ».

If at least one of the reasons available after filtering is not equal to sensitive, access to the content must be completely restricted, showing the error specified in restrictionReason.text.

If the only reason is equal to sensitive, and the need_age_video_verification » client configuration key is not set or equal to false, age verification is disabled and the content may be accessed, provided it's hidden behind a 18+ spoiler.

If the only reason is equal to sensitive, and the need_age_video_verification » client configuration key is equal to true, the content may only be accessed after age verification, initiated by clicking on the 18+ spoiler.

The following client configuration parameters » are used to implement age verification:

- need_age_video_verification » - Specifies whether age verification is required in the current jurisdiction; can be false also if the user has successfully passed age verification.

- verify_age_country » - Unique name for the country or region whose legislation required age verification.

- verify_age_min » - Contains the minimum age required to view sensitive content

- verify_age_bot_username » - Contains the username of the bot whose Main Mini App must be opened in order to proceed with age verification.

- Note: only during age verification, all permission requests from the age verification Mini App (camera, microphone, etc) should be unconditionally allowed, without user interaction (except when required by the OS); video and audio playback without user interaction should also be allowed unconditionally.

- Upon successful or unsuccessful verification, the mini app will emit a web_app_verify_age event, containing info about the detected age.

