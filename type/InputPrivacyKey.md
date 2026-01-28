# InputPrivacyKey
Privacy keys together with privacy rules » indicate what can or can't someone do and are specified by a PrivacyKey constructor, and its input counterpart InputPrivacyKey.

```
inputPrivacyKeyStatusTimestamp#4f96cb18 = InputPrivacyKey;
inputPrivacyKeyChatInvite#bdfb0426 = InputPrivacyKey;
inputPrivacyKeyPhoneCall#fabadc5f = InputPrivacyKey;
inputPrivacyKeyPhoneP2P#db9e70d2 = InputPrivacyKey;
inputPrivacyKeyForwards#a4dd4c08 = InputPrivacyKey;
inputPrivacyKeyProfilePhoto#5719bacc = InputPrivacyKey;
inputPrivacyKeyPhoneNumber#352dafa = InputPrivacyKey;
inputPrivacyKeyAddedByPhone#d1219bdd = InputPrivacyKey;
inputPrivacyKeyVoiceMessages#aee69d68 = InputPrivacyKey;
inputPrivacyKeyAbout#3823cc40 = InputPrivacyKey;
inputPrivacyKeyBirthday#d65a11cc = InputPrivacyKey;
inputPrivacyKeyStarGiftsAutoSave#e1732341 = InputPrivacyKey;
inputPrivacyKeyNoPaidMessages#bdc597b4 = InputPrivacyKey;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputPrivacyKeyStatusTimestamp | Whether people will be able to see our exact last online timestamp.Note that if we decide to hide our exact last online timestamp to someone (i.e., users A, B, C, or all users) and we do not have a Premium subscription, we won't be able to see the exact last online timestamp of those users (A, B, C, or all users), even if those users do share it with us.If those users do share their exact online status with us, but we can't see it due to the reason mentioned above, the by_me flag of userStatusRecently, userStatusLastWeek, userStatusLastMonth will be set. |
| inputPrivacyKeyChatInvite | Whether people will be able to invite you to chats |
| inputPrivacyKeyPhoneCall | Whether you will accept phone calls |
| inputPrivacyKeyPhoneP2P | Whether to allow P2P communication during VoIP calls |
| inputPrivacyKeyForwards | Whether messages forwarded from you will be anonymous |
| inputPrivacyKeyProfilePhoto | Whether people will be able to see your profile picture |
| inputPrivacyKeyPhoneNumber | Whether people will be able to see your phone number |
| inputPrivacyKeyAddedByPhone | Whether people can add you to their contact list by your phone number |
| inputPrivacyKeyVoiceMessages | Whether people can send you voice messages or round videos (Premium users only). |
| inputPrivacyKeyAbout | Whether people can see your bio |
| inputPrivacyKeyBirthday | Whether the user can see our birthday. |
| inputPrivacyKeyStarGiftsAutoSave | Whether received gifts will be automatically displayed on our profile |
| inputPrivacyKeyNoPaidMessages | Who can send you messages without paying, if paid messages » are enabled. |


## Methods
| Method | Description |
| ---- | ----------- |


