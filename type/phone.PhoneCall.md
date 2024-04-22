# Phone.PhoneCall
Phone call

```
phone.phoneCall#ec82e140 phone_call:PhoneCall users:Vector<User> = phone.PhoneCall;

---functions---

phone.requestCall#42ff96ed flags:# video:flags.0?true user_id:InputUser random_id:int g_a_hash:bytes protocol:PhoneCallProtocol = phone.PhoneCall;
phone.acceptCall#3bd2b4a0 peer:InputPhoneCall g_b:bytes protocol:PhoneCallProtocol = phone.PhoneCall;
phone.confirmCall#2efe1722 peer:InputPhoneCall g_a:bytes key_fingerprint:long protocol:PhoneCallProtocol = phone.PhoneCall;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| phone.phoneCall | A VoIP phone call |


## Methods
| Method | Description |
| ---- | ----------- |
| phone.requestCall | Start a telegram phone call |
| phone.acceptCall | Accept incoming call |
| phone.confirmCall | Complete phone call E2E encryption key exchange » |


