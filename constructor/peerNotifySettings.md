# peerNotifySettings
Notification settings.

```
peerNotifySettings#99622c0c flags:# show_previews:flags.0?Bool silent:flags.1?Bool mute_until:flags.2?int ios_sound:flags.3?NotificationSound android_sound:flags.4?NotificationSound other_sound:flags.5?NotificationSound stories_muted:flags.6?Bool stories_hide_sender:flags.7?Bool stories_ios_sound:flags.8?NotificationSound stories_android_sound:flags.9?NotificationSound stories_other_sound:flags.10?NotificationSound = PeerNotifySettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| show_previews | flags.0?Bool | (Ternary value) If set, indicates whether or not to display previews of messages in notifications; otherwise the default behavior should be used. |
| silent | flags.1?Bool | (Ternary value) If set, indicates whether to mute or unmute the peer; otherwise the default behavior should be used. |
| mute_until | flags.2?int | Mute all notifications until this date |
| ios_sound | flags.3?NotificationSound | Notification sound for the official iOS application |
| android_sound | flags.4?NotificationSound | Notification sound for the official android application |
| other_sound | flags.5?NotificationSound | Notification sound for other applications |
| stories_muted | flags.6?Bool | Whether story notifications should be disabled. |
| stories_hide_sender | flags.7?Bool | Whether the sender name should be displayed in story notifications. |
| stories_ios_sound | flags.8?NotificationSound | Sound for story notifications on the official iOS application |
| stories_android_sound | flags.9?NotificationSound | Sound for story notifications on the official Android application |
| stories_other_sound | flags.10?NotificationSound | Sound for story notifications on other applications |


## Type
PeerNotifySettings

## Related pages
