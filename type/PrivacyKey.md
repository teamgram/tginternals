# PrivacyKey
Privacy keys together with privacy rules » indicate what can or can't someone do and are specified by a PrivacyKey constructor, and its input counterpart InputPrivacyKey.

```
privacyKeyStatusTimestamp#bc2eab30 = PrivacyKey;
privacyKeyChatInvite#500e6dfa = PrivacyKey;
privacyKeyPhoneCall#3d662b7b = PrivacyKey;
privacyKeyPhoneP2P#39491cc8 = PrivacyKey;
privacyKeyForwards#69ec56a3 = PrivacyKey;
privacyKeyProfilePhoto#96151fed = PrivacyKey;
privacyKeyPhoneNumber#d19ae46d = PrivacyKey;
privacyKeyAddedByPhone#42ffd42b = PrivacyKey;
privacyKeyVoiceMessages#697f414 = PrivacyKey;
privacyKeyAbout#a486b761 = PrivacyKey;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| privacyKeyStatusTimestamp | Whether we can see the last online timestamp of this user |
| privacyKeyChatInvite | Whether the user can be invited to chats |
| privacyKeyPhoneCall | Whether the user accepts phone calls |
| privacyKeyPhoneP2P | Whether P2P connections in phone calls with this user are allowed |
| privacyKeyForwards | Whether messages forwarded from the user will be anonymously forwarded |
| privacyKeyProfilePhoto | Whether the profile picture of the user is visible |
| privacyKeyPhoneNumber | Whether the user allows us to see his phone number |
| privacyKeyAddedByPhone | Whether this user can be added to our contact list by their phone number |
| privacyKeyVoiceMessages | Whether the user accepts voice messages |
| privacyKeyAbout | Whether people can see your bio |


## Methods
| Method | Description |
| ---- | ----------- |


