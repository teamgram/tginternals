# stories.canSendStory
Check whether we can post stories as the specified peer.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stories.canSendStory#c7dfdfdd peer:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer from which we wish to post stories. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOOSTS_REQUIRED | The specified channel must first be boosted by its users in order to perform this action. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |
| 400 | STORIES_TOO_MUCH | You have hit the maximum active stories limit as specified by the story_expiring_limit_* client configuration parameters: you should buy a Premium subscription, delete an active story, or wait for the oldest story to expire. |
| 400 | STORY_SEND_FLOOD_MONTHLY_%d | You've hit the monthly story limit as specified by the stories_sent_monthly_limit_* client configuration parameters: wait for the specified number of seconds before posting a new story. |
| 400 | STORY_SEND_FLOOD_WEEKLY_%d | You've hit the weekly story limit as specified by the stories_sent_weekly_limit_* client configuration parameters: wait for the specified number of seconds before posting a new story. |

