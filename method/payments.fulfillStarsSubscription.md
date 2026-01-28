# payments.fulfillStarsSubscription
Re-join a private channel associated to an active Telegram Star subscription ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.fulfillStarsSubscription#cc5bebb3 peer:InputPeer subscription_id:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Always pass inputPeerSelf. |
| subscription_id | string | ID of the subscription. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

