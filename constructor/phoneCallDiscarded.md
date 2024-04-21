# phoneCallDiscarded
Indicates a discarded phone call

```
phoneCallDiscarded#50ca4de1 flags:# need_rating:flags.2?true need_debug:flags.3?true video:flags.6?true id:long reason:flags.0?PhoneCallDiscardReason duration:flags.1?int = PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| need_rating | flags.2?true | Whether the server required the user to rate the call |
| need_debug | flags.3?true | Whether the server required the client to send the libtgvoip call debug data |
| video | flags.6?true | Whether the call was a video call |
| id | long | Call ID |
| reason | flags.0?PhoneCallDiscardReason | Why was the phone call discarded |
| duration | flags.1?int | Duration of the phone call in seconds |


## Type
PhoneCall

## Related pages
