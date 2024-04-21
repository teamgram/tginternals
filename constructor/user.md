# user
Indicates info about a certain user

```
user#215c4438 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor = User;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| self | flags.10?true | Whether this user indicates the currently logged in user |
| contact | flags.11?true | Whether this user is a contact |
| mutual_contact | flags.12?true | Whether this user is a mutual contact |
| deleted | flags.13?true | Whether the account of this user was deleted |
| bot | flags.14?true | Is this user a bot? |
| bot_chat_history | flags.15?true | Can the bot see all messages in groups? |
| bot_nochats | flags.16?true | Can the bot be added to groups? |
| verified | flags.17?true | Whether this user is verified |
| restricted | flags.18?true | Access to this user must be restricted for the reason specified in restriction_reason |
| min | flags.20?true | See min |
| bot_inline_geo | flags.21?true | Whether the bot can request our geolocation in inline mode |
| support | flags.23?true | Whether this is an official support user |
| scam | flags.24?true | This may be a scam user |
| apply_min_photo | flags.25?true | If set, the profile picture for this user should be refetched |
| fake | flags.26?true | If set, this user was reported by many users as a fake or scam user: be careful when interacting with them. |
| bot_attach_menu | flags.27?true | Whether this bot offers an attachment menu web app |
| premium | flags.28?true | Whether this user is a Telegram Premium user |
| attach_menu_enabled | flags.29?true | Whether we installed the attachment menu web app offered by this bot |
| flags2 | # | Flags, see TL conditional fields |
| bot_can_edit | flags2.1?true | Whether we can edit the profile picture, name, about text and description of this bot because we own it. |
| close_friend | flags2.2?true | Whether we marked this user as a close friend, see here » for more info |
| stories_hidden | flags2.3?true | Whether we have hidden » all active stories of this user. |
| stories_unavailable | flags2.4?true | No stories from this user are visible. |
| id | long | ID of the user |
| access_hash | flags.0?long | Access hash of the user |
| first_name | flags.1?string | First name |
| last_name | flags.2?string | Last name |
| username | flags.3?string | Username |
| phone | flags.4?string | Phone number |
| photo | flags.5?UserProfilePhoto | Profile picture of user |
| status | flags.6?UserStatus | Online status of user |
| bot_info_version | flags.14?int | Version of the bot_info field in userFull, incremented every time it changes |
| restriction_reason | flags.18?Vector<RestrictionReason> | Contains the reason why access to this user must be restricted. |
| bot_inline_placeholder | flags.19?string | Inline placeholder for this inline bot |
| lang_code | flags.22?string | Language code of the user |
| emoji_status | flags.30?EmojiStatus | Emoji status |
| usernames | flags2.0?Vector<Username> | Additional usernames |
| stories_max_id | flags2.5?int | ID of the maximum read story. |
| color | flags2.8?PeerColor | The user's accent color. |
| profile_color | flags2.9?PeerColor | The user's profile color. |


## Type
User

## Related pages
