# account.SavedRingtone
Contains information about a saved notification sound

```
account.savedRingtone#b7263f6d = account.SavedRingtone;
account.savedRingtoneConverted#1f307eb7 document:Document = account.SavedRingtone;

---functions---

account.saveRingtone#3dea5b03 id:InputDocument unsave:Bool = account.SavedRingtone;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| account.savedRingtone | The notification sound was already in MP3 format and was saved without any modification |
| account.savedRingtoneConverted | The notification sound was not in MP3 format and was successfully converted and saved, use the returned Document to refer to the notification sound from now on |


## Methods
| Method | Description |
| ---- | ----------- |
| account.saveRingtone | Save or remove saved notification sound.If the notification sound is already in MP3 format, account.savedRingtone will be returned.  Otherwise, it will be automatically converted and a account.savedRingtoneConverted will be returned, containing a new document object that should be used to refer to the ringtone from now on (ie when deleting it using the unsave parameter, or when downloading it). |


