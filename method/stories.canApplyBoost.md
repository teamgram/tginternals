# stories.canApplyBoost
Check whether a channel can be boosted, see here for more info ».

```
Method schema is available as of layer 166. Switch »
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The channel to boost. |


## Result
 

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOOST_NOT_MODIFIED | You're already boosting the specified channel. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |

