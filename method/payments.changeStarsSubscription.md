# payments.changeStarsSubscription
Activate or deactivate a Telegram Star subscription ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.changeStarsSubscription#c7770878 flags:# peer:InputPeer subscription_id:string canceled:flags.0?Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Always pass inputPeerSelf. |
| subscription_id | string | ID of the subscription. |
| canceled | flags.0?Bool | Whether to cancel or reactivate the subscription. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

