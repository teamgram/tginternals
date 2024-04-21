# userFull
Extended user info

```
userFull#b9b12c6c flags:# blocked:flags.0?true phone_calls_available:flags.4?true phone_calls_private:flags.5?true can_pin_message:flags.7?true has_scheduled:flags.12?true video_calls_available:flags.13?true voice_messages_forbidden:flags.20?true translations_disabled:flags.23?true stories_pinned_available:flags.26?true blocked_my_stories_from:flags.27?true wallpaper_overridden:flags.28?true id:long about:flags.1?string settings:PeerSettings personal_photo:flags.21?Photo profile_photo:flags.2?Photo fallback_photo:flags.22?Photo notify_settings:PeerNotifySettings bot_info:flags.3?BotInfo pinned_msg_id:flags.6?int common_chats_count:int folder_id:flags.11?int ttl_period:flags.14?int theme_emoticon:flags.15?string private_forward_name:flags.16?string bot_group_admin_rights:flags.17?ChatAdminRights bot_broadcast_admin_rights:flags.18?ChatAdminRights premium_gifts:flags.19?Vector<PremiumGiftOption> wallpaper:flags.24?WallPaper stories:flags.25?PeerStories = UserFull;
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
| theme_emoticon | flags.15?string | Emoji associated with chat theme |
| private_forward_name | flags.16?string | Anonymized text to be shown instead of the user's name on forwarded messages |
| bot_group_admin_rights | flags.17?ChatAdminRights | A suggested set of administrator rights for the bot, to be shown when adding the bot as admin to a group, see here for more info on how to handle them ». |
| bot_broadcast_admin_rights | flags.18?ChatAdminRights | A suggested set of administrator rights for the bot, to be shown when adding the bot as admin to a channel, see here for more info on how to handle them ». |
| premium_gifts | flags.19?Vector<PremiumGiftOption> | Telegram Premium subscriptions gift options |
| wallpaper | flags.24?WallPaper | Wallpaper to use in the private chat with the user. |
| stories | flags.25?PeerStories | Active stories » |


## Type
UserFull

## Related pages
