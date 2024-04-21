# account.setGlobalPrivacySettings
Set global privacy settings

```
globalPrivacySettings#734c4ccb flags:# archive_and_mute_new_noncontact_peers:flags.0?true keep_archived_unmuted:flags.1?true keep_archived_folders:flags.2?true = GlobalPrivacySettings;
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
| 400 | AUTOARCHIVE_NOT_AVAILABLE | The autoarchive setting is not available at this time: please check the value of the autoarchive_setting_available field in client config » before calling this method. |

