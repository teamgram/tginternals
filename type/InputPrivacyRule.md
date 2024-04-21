# InputPrivacyRule
Privacy rules indicate who can or can't do something and are specified by a PrivacyRule, and its input counterpart InputPrivacyRule.

```
inputPrivacyValueAllowContacts#d09e07b = InputPrivacyRule;
inputPrivacyValueAllowAll#184b35ce = InputPrivacyRule;
inputPrivacyValueAllowUsers#131cc67f users:Vector<InputUser> = InputPrivacyRule;
inputPrivacyValueDisallowContacts#ba52007 = InputPrivacyRule;
inputPrivacyValueDisallowAll#d66b66c9 = InputPrivacyRule;
inputPrivacyValueDisallowUsers#90110467 users:Vector<InputUser> = InputPrivacyRule;
inputPrivacyValueAllowChatParticipants#840649cf chats:Vector<long> = InputPrivacyRule;
inputPrivacyValueDisallowChatParticipants#e94f0f86 chats:Vector<long> = InputPrivacyRule;
inputPrivacyValueAllowCloseFriends#2f453e49 = InputPrivacyRule;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputPrivacyValueAllowContacts | Allow only contacts |
| inputPrivacyValueAllowAll | Allow all users |
| inputPrivacyValueAllowUsers | Allow only certain users |
| inputPrivacyValueDisallowContacts | Disallow only contacts |
| inputPrivacyValueDisallowAll | Disallow all |
| inputPrivacyValueDisallowUsers | Disallow only certain users |
| inputPrivacyValueAllowChatParticipants | Allow only participants of certain chats |
| inputPrivacyValueDisallowChatParticipants | Disallow only participants of certain chats |
| inputPrivacyValueAllowCloseFriends | Allow only close friends » |


## Methods
| Method | Description |
| ---- | ----------- |


