# OutboxReadDate
Exact read date of a private message we sent to another user.

```
outboxReadDate#3bb842ac date:int = OutboxReadDate;

---functions---

messages.getOutboxReadDate#8c4bfe5d peer:InputPeer msg_id:int = OutboxReadDate;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| outboxReadDate | Exact read date of a private message we sent to another user. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getOutboxReadDate | Get the exact read date of one of our messages, sent to a private chat with another user.Can be only done for private outgoing messages not older than appConfig.pm_read_date_expire_period ».If the peer's userFull.read_dates_private flag is set, we will not be able to fetch the exact read date of messages we send to them, and a USER_PRIVACY_RESTRICTED RPC error will be emitted.  The exact read date of messages might still be unavailable for other reasons, see here » for more info.  To set userFull.read_dates_private for ourselves invoke account.setGlobalPrivacySettings, setting the settings.hide_read_marks flag. |


