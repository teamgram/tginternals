# chatlists.exportChatlistInvite
Export a folder », creating a chat folder deep link ».

```
chatlists.exportedChatlistInvite#10e6e3a6 filter:DialogFilter invite:ExportedChatlistInvite = chatlists.ExportedChatlistInvite;
---functions---
chatlists.exportChatlistInvite#8472478e chatlist:InputChatlist title:string peers:Vector<InputPeer> = chatlists.ExportedChatlistInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chatlist | InputChatlist | The folder to export |
| title | string | An optional name for the link |
| peers | Vector<InputPeer> | The list of channels, group and supergroups to share with the link. Basic groups will automatically be converted to supergroups when invoking the method. |


## Result
chatlists.ExportedChatlistInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILTER_ID_INVALID | The specified filter ID is invalid. |
| 400 | FILTER_NOT_SUPPORTED | The specified filter cannot be used in this context. |
| 400 | INVITES_TOO_MUCH | The maximum number of per-folder invites specified by the chatlist_invites_limit_default/chatlist_invites_limit_premium client configuration parameters » was reached. |
| 400 | PEERS_LIST_EMPTY | The specified list of peers is empty. |

