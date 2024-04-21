# PrivacyRule
Privacy rules together with privacy keys indicate what can or can't someone do and are specified by a PrivacyRule constructor, and its input counterpart InputPrivacyRule.

```
privacyValueAllowContacts#fffe1bac = PrivacyRule;
privacyValueAllowAll#65427b82 = PrivacyRule;
privacyValueAllowUsers#b8905fb2 users:Vector<long> = PrivacyRule;
privacyValueDisallowContacts#f888fa1a = PrivacyRule;
privacyValueDisallowAll#8b73e763 = PrivacyRule;
privacyValueDisallowUsers#e4621141 users:Vector<long> = PrivacyRule;
privacyValueAllowChatParticipants#6b134e8e chats:Vector<long> = PrivacyRule;
privacyValueDisallowChatParticipants#41c87565 chats:Vector<long> = PrivacyRule;
privacyValueAllowCloseFriends#f7e8d89b = PrivacyRule;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| privacyValueAllowContacts | Allow all contacts |
| privacyValueAllowAll | Allow all users |
| privacyValueAllowUsers | Allow only certain users |
| privacyValueDisallowContacts | Disallow only contacts |
| privacyValueDisallowAll | Disallow all users |
| privacyValueDisallowUsers | Disallow only certain users |
| privacyValueAllowChatParticipants | Allow all participants of certain chats |
| privacyValueDisallowChatParticipants | Disallow only participants of certain chats |
| privacyValueAllowCloseFriends | Allow only close friends » |


## Methods
| Method | Description |
| ---- | ----------- |


