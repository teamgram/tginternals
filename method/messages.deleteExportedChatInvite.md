# messages.deleteExportedChatInvite
Delete a chat invite

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.deleteExportedChatInvite#d464a42b peer:InputPeer link:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer |
| link | string | Invite link |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | INVITE_HASH_EXPIRED | The invite link has expired. |
| 400 | INVITE_REVOKED_MISSING | The specified invite link was already revoked or is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

