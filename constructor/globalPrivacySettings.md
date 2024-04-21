# globalPrivacySettings
Global privacy settings

```
globalPrivacySettings#734c4ccb flags:# archive_and_mute_new_noncontact_peers:flags.0?true keep_archived_unmuted:flags.1?true keep_archived_folders:flags.2?true = GlobalPrivacySettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| archive_and_mute_new_noncontact_peers | flags.0?true | Whether to archive and mute new chats from non-contacts |
| keep_archived_unmuted | flags.1?true | Whether unmuted chats will be kept in the Archive chat list when they get a new message. |
| keep_archived_folders | flags.2?true | Whether unmuted chats that are always included or pinned in a folder, will be kept in the Archive chat list when they get a new message. Ignored if keep_archived_unmuted is set. |


## Type
GlobalPrivacySettings

## Related pages
