# decryptedMessageActionResend
Request for the other party in a Secret Chat to automatically resend a contiguous range of previously sent messages, as explained in Sequence number is Secret Chats.

```
===17===
decryptedMessageActionResend#511110b0 start_seq_no:int end_seq_no:int = DecryptedMessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| start_seq_no | int | out_seq_no of the first message to be resent, with correct parity |
| end_seq_no | int | out_seq_no of the last message to be resent, with same parity. |


## Type
DecryptedMessageAction

## Related pages
