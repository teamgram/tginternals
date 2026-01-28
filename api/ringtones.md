# Ringtones

The API allows uploading and synchronizing notification sounds associated to a specific chat.

### Uploading notification sounds

Schema:

```
account.savedRingtonesNotModified#fbf6e8b1 = account.SavedRingtones;
account.savedRingtones#c1e92cc5 hash:long ringtones:Vector<Document> = account.SavedRingtones;

updateSavedRingtones#74d8be99 = Update;

account.savedRingtone#b7263f6d = account.SavedRingtone;
account.savedRingtoneConverted#1f307eb7 document:Document = account.SavedRingtone;

---functions---

account.uploadRingtone#831a83a2 file:InputFile file_name:string mime_type:string = Document;
account.saveRingtone#3dea5b03 id:InputDocument unsave:Bool = account.SavedRingtone;
account.getSavedRingtones#e1902288 hash:long = account.SavedRingtones;
```

A notification sound file may be uploaded using account.uploadRingtone.
After upload, the document should be provided to account.saveRingtone to save the notification sound, returning a simple account.savedRingtone.

Supported formats:

- MP3

- OGG OPUS

An existing voice message may also be passed directly to account.saveRingtone.
When passing existing voice messages to account.saveRingtone an account.savedRingtoneConverted constructor will be returned containing the new document to use instead of the original voice message document when removing or using notification sounds.

The following ringtone limits are specified in the client configuration:

- ringtone_duration_max - The maximum duration in seconds of uploaded ringtones

- ringtone_saved_count_max - The maximum number of saveable ringtones

- ringtone_size_max - The maximum (post-conversion) filesize in bytes of uploadable ringtones

### Removing notification sounds

Schema:

```
account.savedRingtone#b7263f6d = account.SavedRingtone;

---functions---

account.saveRingtone#3dea5b03 id:InputDocument unsave:Bool = account.SavedRingtone;
```

Pass true to unsave in account.saveRingtone to remove an uploaded notification sound.

### Getting notification sounds

Schema:

```
updateSavedRingtones#74d8be99 = Update;

account.savedRingtonesNotModified#fbf6e8b1 = account.SavedRingtones;
account.savedRingtones#c1e92cc5 hash:long ringtones:Vector<Document> = account.SavedRingtones;

---functions---

account.getSavedRingtones#e1902288 hash:long = account.SavedRingtones;
```

account.getSavedRingtones can be used to obtain all saved notification sounds.
The client will receive an updateSavedRingtones update if the list is modified by the user on other clients, which should trigger a call to account.getSavedRingtones.

### Setting notification sounds

Schema:

```
notificationSoundDefault#97e8bebe = NotificationSound;
notificationSoundNone#6f0c34df = NotificationSound;
notificationSoundLocal#830b9ae4 title:string data:string = NotificationSound;
notificationSoundRingtone#ff6c8049 id:long = NotificationSound;

inputNotifyPeer#b8bc5b0c peer:InputPeer = InputNotifyPeer;
inputNotifyUsers#193b4417 = InputNotifyPeer;
inputNotifyChats#4a95e84e = InputNotifyPeer;
inputNotifyBroadcasts#b1db7c7e = InputNotifyPeer;

inputPeerNotifySettings#cacb6ae2 flags:# show_previews:flags.0?Bool silent:flags.1?Bool mute_until:flags.2?int sound:flags.3?NotificationSound stories_muted:flags.6?Bool stories_hide_sender:flags.7?Bool stories_sound:flags.8?NotificationSound = InputPeerNotifySettings;

---functions---

account.updateNotifySettings#84be5b93 peer:InputNotifyPeer settings:InputPeerNotifySettings = Bool;
```

To set the notification sound to play when receiving messages from a specific peer or from a category of peers, use account.updateNotifySettings, populating the ios_sound, android_sound or other_sound fields according to the platform where the sound should be played.

The fields can be populated with the following constructors:

- notificationSoundDefault - The default notification sound should be played

- notificationSoundNone - No notification sound should be played

- notificationSoundRingtone - A previously uploaded notification sound identified by the uploaded/converted document id should be played.

- notificationSoundLocal - A local notification sound (possibly provided by the OS) identified by the client-specific data payload should be played.

