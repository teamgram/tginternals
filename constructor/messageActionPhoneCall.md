# messageActionPhoneCall
A phone call

```
messageActionPhoneCall#80e11a7f flags:# video:flags.2?true call_id:long reason:flags.0?PhoneCallDiscardReason duration:flags.1?int = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| video | flags.2?true | Is this a video call? |
| call_id | long | Call ID |
| reason | flags.0?PhoneCallDiscardReason | If the call has ended, the reason why it ended |
| duration | flags.1?int | Duration of the call in seconds |


## Type
MessageAction

## Related pages
