# account.setGlobalPrivacySettings
Set global privacy settings

```
globalPrivacySettings#fe41b34f flags:# archive_and_mute_new_noncontact_peers:flags.0?true keep_archived_unmuted:flags.1?true keep_archived_folders:flags.2?true hide_read_marks:flags.3?true new_noncontact_peers_require_premium:flags.4?true display_gifts_button:flags.7?true noncontact_peers_paid_stars:flags.5?long disallowed_gifts:flags.6?DisallowedGiftsSettings = GlobalPrivacySettings;
---functions---
account.setGlobalPrivacySettings#1edaaac2 settings:GlobalPrivacySettings = GlobalPrivacySettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| settings | GlobalPrivacySettings | Global privacy settings |


## Result
GlobalPrivacySettings

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | AUTOARCHIVE_NOT_AVAILABLE | The autoarchive setting is not available at this time: please check the value of the autoarchive_setting_available field in client config » before calling this method. |
| 403 | BOT_ACCESS_FORBIDDEN | The specified method can be used over a business connection for some operations, but the specified query attempted an operation that is not allowed over a business connection. |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |

