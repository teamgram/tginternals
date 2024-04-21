# bots.setBotBroadcastDefaultAdminRights
Set the default suggested admin rights for bots being added as admins to channels, see here for more info on how to handle them ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.setBotBroadcastDefaultAdminRights#788464e1 admin_rights:ChatAdminRights = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| admin_rights | ChatAdminRights | Admin rights |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | RIGHTS_NOT_MODIFIED | The new admin rights are equal to the old rights, no change was made. |

