# userFull
Extended user info

```
userFull#c577b5ad flags:# blocked:flags.0?true phone_calls_available:flags.4?true phone_calls_private:flags.5?true can_pin_message:flags.7?true has_scheduled:flags.12?true video_calls_available:flags.13?true voice_messages_forbidden:flags.20?true translations_disabled:flags.23?true stories_pinned_available:flags.26?true blocked_my_stories_from:flags.27?true wallpaper_overridden:flags.28?true contact_require_premium:flags.29?true read_dates_private:flags.30?true flags2:# sponsored_enabled:flags2.7?true can_view_revenue:flags2.9?true bot_can_manage_emoji_status:flags2.10?true display_gifts_button:flags2.16?true id:long about:flags.1?string settings:PeerSettings personal_photo:flags.21?Photo profile_photo:flags.2?Photo fallback_photo:flags.22?Photo notify_settings:PeerNotifySettings bot_info:flags.3?BotInfo pinned_msg_id:flags.6?int common_chats_count:int folder_id:flags.11?int ttl_period:flags.14?int theme:flags.15?ChatTheme private_forward_name:flags.16?string bot_group_admin_rights:flags.17?ChatAdminRights bot_broadcast_admin_rights:flags.18?ChatAdminRights wallpaper:flags.24?WallPaper stories:flags.25?PeerStories business_work_hours:flags2.0?BusinessWorkHours business_location:flags2.1?BusinessLocation business_greeting_message:flags2.2?BusinessGreetingMessage business_away_message:flags2.3?BusinessAwayMessage business_intro:flags2.4?BusinessIntro birthday:flags2.5?Birthday personal_channel_id:flags2.6?long personal_channel_message:flags2.6?int stargifts_count:flags2.8?int starref_program:flags2.11?StarRefProgram bot_verification:flags2.12?BotVerification send_paid_messages_stars:flags2.14?long disallowed_gifts:flags2.15?DisallowedGiftsSettings stars_rating:flags2.17?StarsRating stars_my_pending_rating:flags2.18?StarsRating stars_my_pending_rating_date:flags2.18?int main_tab:flags2.20?ProfileTab saved_music:flags2.21?Document = UserFull;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| blocked | flags.0?true | Whether you have blocked this user |
| phone_calls_available | flags.4?true | Whether this user can make VoIP calls |
| phone_calls_private | flags.5?true | Whether this user's privacy settings allow you to call them |
| can_pin_message | flags.7?true | Whether you can pin messages in the chat with this user, you can do this only for a chat with yourself |
| has_scheduled | flags.12?true | Whether scheduled messages are available |
| video_calls_available | flags.13?true | Whether the user can receive video calls |
| voice_messages_forbidden | flags.20?true | Whether this user doesn't allow sending voice messages in a private chat with them |
| translations_disabled | flags.23?true | Whether the real-time chat translation popup should be hidden. |
| stories_pinned_available | flags.26?true | Whether this user has some pinned stories. |
| blocked_my_stories_from | flags.27?true | Whether we've blocked this user, preventing them from seeing our stories ». |
| wallpaper_overridden | flags.28?true | Whether the other user has chosen a custom wallpaper for us using messages.setChatWallPaper and the for_both flag, see here » for more info. |
| contact_require_premium | flags.29?true | If set, we cannot write to this user: subscribe to Telegram Premium to get permission to write to this user. To set this flag for ourselves invoke account.setGlobalPrivacySettings, setting the settings.new_noncontact_peers_require_premium flag, see here » for more info. |
| read_dates_private | flags.30?true | If set, we cannot fetch the exact read date of messages we send to this user using messages.getOutboxReadDate.  The exact read date of messages might still be unavailable for other reasons, see here » for more info.  To set this flag for ourselves invoke account.setGlobalPrivacySettings, setting the settings.hide_read_marks flag. |
| flags2 | # | Flags, see TL conditional fields |
| sponsored_enabled | flags2.7?true | Whether ads were re-enabled for the current account (only accessible to the currently logged-in user), see here » for more info. |
| can_view_revenue | flags2.9?true | If set, this user can view ad revenue statistics » for this bot. |
| bot_can_manage_emoji_status | flags2.10?true | If set, this is a bot that can change our emoji status » |
| display_gifts_button | flags2.16?true | If this flag is set for both us and another user (changed through globalPrivacySettings), a gift button should always be displayed in the text field in private chats with the other user: once clicked, the gift UI should be displayed, offering the user options to gift Telegram Premium » subscriptions or Telegram Gifts ». |
| id | long | User ID |
| about | flags.1?string | Bio of the user |
| settings | PeerSettings | Peer settings |
| personal_photo | flags.21?Photo | Personal profile photo, to be shown instead of profile_photo. |
| profile_photo | flags.2?Photo | Profile photo |
| fallback_photo | flags.22?Photo | Fallback profile photo, displayed if no photo is present in profile_photo or personal_photo, due to privacy settings. |
| notify_settings | PeerNotifySettings | Notification settings |
| bot_info | flags.3?BotInfo | For bots, info about the bot (bot commands, etc) |
| pinned_msg_id | flags.6?int | Message ID of the last pinned message |
| common_chats_count | int | Chats in common with this user |
| folder_id | flags.11?int | Peer folder ID, for more info click here |
| ttl_period | flags.14?int | Time To Live of all messages in this chat; once a message is this many seconds old, it must be deleted. |
| theme | flags.15?ChatTheme | The chat theme associated with this user ». |
| private_forward_name | flags.16?string | Anonymized text to be shown instead of the user's name on forwarded messages |
| bot_group_admin_rights | flags.17?ChatAdminRights | A suggested set of administrator rights for the bot, to be shown when adding the bot as admin to a group, see here for more info on how to handle them ». |
| bot_broadcast_admin_rights | flags.18?ChatAdminRights | A suggested set of administrator rights for the bot, to be shown when adding the bot as admin to a channel, see here for more info on how to handle them ». |
| wallpaper | flags.24?WallPaper | Wallpaper to use in the private chat with the user. |
| stories | flags.25?PeerStories | Active stories » |
| business_work_hours | flags2.0?BusinessWorkHours | Telegram Business working hours ». |
| business_location | flags2.1?BusinessLocation | Telegram Business location ». |
| business_greeting_message | flags2.2?BusinessGreetingMessage | Telegram Business greeting message ». |
| business_away_message | flags2.3?BusinessAwayMessage | Telegram Business away message ». |
| business_intro | flags2.4?BusinessIntro | Specifies a custom Telegram Business profile introduction ». |
| birthday | flags2.5?Birthday | Contains info about the user's birthday ». |
| personal_channel_id | flags2.6?long | ID of the associated personal channel », that should be shown in the profile page. |
| personal_channel_message | flags2.6?int | ID of the latest message of the associated personal channel », that should be previewed in the profile page. |
| stargifts_count | flags2.8?int | Number of gifts the user has chosen to display on their profile |
| starref_program | flags2.11?StarRefProgram | This bot has an active referral program » |
| bot_verification | flags2.12?BotVerification | Describes a bot verification icon ». |
| send_paid_messages_stars | flags2.14?long | If set and bigger than 0, this user has enabled paid messages » and we must pay the specified amount of Stars to send messages to them, see here » for the full flow. If set and equal to 0, the user requires payment in general but we were exempted from paying for any of the reasons specified in the docs ». |
| disallowed_gifts | flags2.15?DisallowedGiftsSettings | Disallows the reception of specific gift types. |
| stars_rating | flags2.17?StarsRating | The user's star rating. |
| stars_my_pending_rating | flags2.18?StarsRating | Our pending star rating, only visible for ourselves. |
| stars_my_pending_rating_date | flags2.18?int | When the pending star rating will be applied, only visible for ourselves. |
| main_tab | flags2.20?ProfileTab | The main tab for the user's profile, see here » for more info. |
| saved_music | flags2.21?Document | The first song on the music tab of the profile, see here » for more info on the music profile tab. |


## Type


## Related pages
