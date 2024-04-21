# account.autoSaveSettings
Contains media autosave settings

```
account.autoSaveSettings#4c3e069d users_settings:AutoSaveSettings chats_settings:AutoSaveSettings broadcasts_settings:AutoSaveSettings exceptions:Vector<AutoSaveException> chats:Vector<Chat> users:Vector<User> = account.AutoSaveSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| users_settings | AutoSaveSettings | Default media autosave settings for private chats |
| chats_settings | AutoSaveSettings | Default media autosave settings for groups and supergroups |
| broadcasts_settings | AutoSaveSettings | Default media autosave settings for channels |
| exceptions | Vector<AutoSaveException> | Peer-specific granular autosave settings |
| chats | Vector<Chat> | Chats mentioned in the peer-specific granular autosave settings |
| users | Vector<User> | Users mentioned in the peer-specific granular autosave settings |


## Type
account.AutoSaveSettings

## Related pages
