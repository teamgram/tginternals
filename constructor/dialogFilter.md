# dialogFilter
Dialog filter AKA folder

```
dialogFilter#7438f7e8 flags:# contacts:flags.0?true non_contacts:flags.1?true groups:flags.2?true broadcasts:flags.3?true bots:flags.4?true exclude_muted:flags.11?true exclude_read:flags.12?true exclude_archived:flags.13?true id:int title:string emoticon:flags.25?string pinned_peers:Vector<InputPeer> include_peers:Vector<InputPeer> exclude_peers:Vector<InputPeer> = DialogFilter;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| contacts | flags.0?true | Whether to include all contacts in this folder |
| non_contacts | flags.1?true | Whether to include all non-contacts in this folder |
| groups | flags.2?true | Whether to include all groups in this folder |
| broadcasts | flags.3?true | Whether to include all channels in this folder |
| bots | flags.4?true | Whether to include all bots in this folder |
| exclude_muted | flags.11?true | Whether to exclude muted chats from this folder |
| exclude_read | flags.12?true | Whether to exclude read chats from this folder |
| exclude_archived | flags.13?true | Whether to exclude archived chats from this folder |
| id | int | Folder ID |
| title | string | Folder name |
| emoticon | flags.25?string | Emoji to use as icon for the folder. |
| pinned_peers | Vector<InputPeer> | Pinned chats, folders can have unlimited pinned chats |
| include_peers | Vector<InputPeer> | Include the following chats in this folder |
| exclude_peers | Vector<InputPeer> | Exclude the following chats from this folder |


## Type
DialogFilter

## Related pages
