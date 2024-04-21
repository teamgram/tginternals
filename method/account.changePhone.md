# account.changePhone
Change the phone number of the current account

```
userEmpty#d3bc4b7a id:long = User;
user#215c4438 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor = User;
---functions---
account.changePhone#70c32edb phone_number:string phone_code_hash:string phone_code:string = User;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | New phone number |
| phone_code_hash | string | Phone code hash received when calling account.sendChangePhoneCode |
| phone_code | string | Phone code received when calling account.sendChangePhoneCode |


## Result
User

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_CODE_EMPTY | phone_code is missing. |
| 400 | PHONE_CODE_EXPIRED | The phone code you provided has expired. |
| 406 | PHONE_NUMBER_INVALID | The phone number is invalid. |
| 400 | PHONE_NUMBER_OCCUPIED | The phone number is already in use. |

