# Ringtones

The API allows uploading and synchronizing notification sounds associated to a specific chat.

### Uploading notification sounds

Schema:

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

Pass true to unsave in account.saveRingtone to remove an uploaded notification sound.

### Getting notification sounds

Schema:

account.getSavedRingtones can be used to obtain all saved notification sounds.
The client will receive an updateSavedRingtones update if the list is modified by the user on other clients, which should trigger a call to account.getSavedRingtones.

### Setting notification sounds

Schema:

To set the notification sound to play when receiving messages from a specific peer or from a category of peers, use account.updateNotifySettings, populating the ios_sound, android_sound or other_sound fields according to the platform where the sound should be played.

The fields can be populated with the following constructors:

- notificationSoundDefault - The default notification sound should be played

- notificationSoundNone - No notification sound should be played

- notificationSoundRingtone - A previously uploaded notification sound identified by the uploaded/converted document id should be played.

- notificationSoundLocal - A local notification sound (possibly provided by the OS) identified by the client-specific data payload should be played.

