# chatlists.editExportedInvite
Edit a chat folder deep link ».

```
exportedChatlistInvite#c5181ac flags:# title:string url:string peers:Vector<Peer> = ExportedChatlistInvite;
---functions---
chatlists.editExportedInvite#653db63d flags:# chatlist:InputChatlist slug:string title:flags.1?string peers:flags.2?Vector<InputPeer> = ExportedChatlistInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| chatlist | InputChatlist | Folder ID |
| slug | string | slug obtained from the chat folder deep link ». |
| title | flags.1?string | If set, sets a new name for the link |
| peers | flags.2?Vector<InputPeer> | If set, changes the list of peers shared with the link |


## Result
ExportedChatlistInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILTER_ID_INVALID | The specified filter ID is invalid. |
| 400 | FILTER_NOT_SUPPORTED | The specified filter cannot be used in this context. |

