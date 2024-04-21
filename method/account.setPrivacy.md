# account.setPrivacy
Change privacy settings of current account

```
account.privacyRules#50a04e45 rules:Vector<PrivacyRule> chats:Vector<Chat> users:Vector<User> = account.PrivacyRules;
---functions---
account.setPrivacy#c9f81ce8 key:InputPrivacyKey rules:Vector<InputPrivacyRule> = account.PrivacyRules;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| key | InputPrivacyKey | New privacy rule |
| rules | Vector<InputPrivacyRule> | Peers to which the privacy rule will apply. |


## Result
account.PrivacyRules

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PRIVACY_KEY_INVALID | The privacy key is invalid. |
| 400 | PRIVACY_TOO_LONG | Too many privacy rules were specified, the current limit is 1000. |
| 400 | PRIVACY_VALUE_INVALID | The specified privacy rule combination is invalid. |

