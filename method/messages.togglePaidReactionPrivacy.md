# messages.togglePaidReactionPrivacy
Changes the privacy of already sent paid reactions on a specific message.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.togglePaidReactionPrivacy#435885b5 peer:InputPeer msg_id:int private:PaidReactionPrivacy = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The channel |
| msg_id | int | The ID of the message to which we sent the paid reactions |
| private | PaidReactionPrivacy | If true, makes the current anonymous in the top sender leaderboard for this message; otherwise, does the opposite. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | REACTION_EMPTY | Empty reaction provided. |

