# globalPrivacySettings
Global privacy settings

```
globalPrivacySettings#fe41b34f flags:# archive_and_mute_new_noncontact_peers:flags.0?true keep_archived_unmuted:flags.1?true keep_archived_folders:flags.2?true hide_read_marks:flags.3?true new_noncontact_peers_require_premium:flags.4?true display_gifts_button:flags.7?true noncontact_peers_paid_stars:flags.5?long disallowed_gifts:flags.6?DisallowedGiftsSettings = GlobalPrivacySettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| archive_and_mute_new_noncontact_peers | flags.0?true | Whether to archive and mute new chats from non-contacts |
| keep_archived_unmuted | flags.1?true | Whether unmuted chats will be kept in the Archive chat list when they get a new message. |
| keep_archived_folders | flags.2?true | Whether unmuted chats that are always included or pinned in a folder, will be kept in the Archive chat list when they get a new message. Ignored if keep_archived_unmuted is set. |
| hide_read_marks | flags.3?true | If this flag is set, the inputPrivacyKeyStatusTimestamp key will also apply to the ability to use messages.getOutboxReadDate on messages sent to us. Meaning, users that cannot see our exact last online date due to the current value of the inputPrivacyKeyStatusTimestamp key will receive a 403 USER_PRIVACY_RESTRICTED error when invoking messages.getOutboxReadDate to fetch the exact read date of a message they sent to us. The userFull.read_dates_private flag will be set for users that have this flag enabled. |
| new_noncontact_peers_require_premium | flags.4?true | See here for more info on this flag ». |
| display_gifts_button | flags.7?true | Enables or disables our userFull.display_gifts_button flag: if the userFull.display_gifts_button flag of both us and another user is set, a gift button should always be displayed in the text field in private chats with the other user: once clicked, the gift UI should be displayed, offering the user options to gift Telegram Premium » subscriptions or Telegram Gifts ». |
| noncontact_peers_paid_stars | flags.5?long | If configured, specifies the number of stars users must pay us to send us a message, see here » for more info on paid messages. |
| disallowed_gifts | flags.6?DisallowedGiftsSettings | Disallows the reception of specific gift types. |


## Type
GlobalPrivacySettings

## Related pages
