# account.getPrivacy
Get privacy settings of current account

```
account.privacyRules#50a04e45 rules:Vector<PrivacyRule> chats:Vector<Chat> users:Vector<User> = account.PrivacyRules;
---functions---
account.getPrivacy#dadbc950 key:InputPrivacyKey = account.PrivacyRules;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| key | InputPrivacyKey | Peer category whose privacy settings should be fetched |


## Result
account.PrivacyRules

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PRIVACY_KEY_INVALID | The privacy key is invalid. |

