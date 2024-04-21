# messages.deleteRevokedExportedChatInvites
Delete all revoked chat invites

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.deleteRevokedExportedChatInvites#56987bd5 peer:InputPeer admin_id:InputUser = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Chat |
| admin_id | InputUser | ID of the admin that originally generated the revoked chat invites |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ADMIN_ID_INVALID | The specified admin ID is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

