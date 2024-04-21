# auth.sentCodeTypeFirebaseSms
An authentication code should be delivered via SMS after Firebase attestation, as described in the auth documentation ».

```
auth.sentCodeTypeFirebaseSms#e57b1432 flags:# nonce:flags.0?bytes receipt:flags.1?string push_timeout:flags.1?int length:int = auth.SentCodeType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| nonce | flags.0?bytes | On Android, the nonce to be used as described in the auth documentation » |
| receipt | flags.1?string | On iOS, must be compared with the receipt extracted from the received push notification. |
| push_timeout | flags.1?int | On iOS: if a push notification with the ios_push_secret isn't received within push_timeout seconds, the next_type authentication method must be used, with auth.resendCode. |
| length | int | Length of the code that will be delivered. |


## Type
auth.SentCodeType

## Related pages
