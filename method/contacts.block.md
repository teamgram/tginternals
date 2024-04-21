# contacts.block
Adds a peer to a blocklist, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
contacts.block#2e2e8734 flags:# my_stories_from:flags.0?true id:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| my_stories_from | flags.0?true | Whether the peer should be added to the story blocklist; if not set, the peer will be added to the main blocklist, see here » for more info. |
| id | InputPeer | Peer |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CONTACT_ID_INVALID | The provided contact ID is invalid. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

