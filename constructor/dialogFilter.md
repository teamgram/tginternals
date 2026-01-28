# dialogFilter
Dialog filter AKA folder

```
dialogFilter#aa472651 flags:# contacts:flags.0?true non_contacts:flags.1?true groups:flags.2?true broadcasts:flags.3?true bots:flags.4?true exclude_muted:flags.11?true exclude_read:flags.12?true exclude_archived:flags.13?true title_noanimate:flags.28?true id:int title:TextWithEntities emoticon:flags.25?string color:flags.27?int pinned_peers:Vector<InputPeer> include_peers:Vector<InputPeer> exclude_peers:Vector<InputPeer> = DialogFilter;
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
| title_noanimate | flags.28?true | If set, any animated emojis present in title should not be animated and should be instead frozen on the first frame. |
| id | int | Folder ID |
| title | TextWithEntities | Folder name (max 12 UTF-8 chars) |
| emoticon | flags.25?string | Emoji to use as icon for the folder. |
| color | flags.27?int | A color ID for the folder tag associated to this folder, see here » for more info. |
| pinned_peers | Vector<InputPeer> | Pinned chats, folders can have unlimited pinned chats |
| include_peers | Vector<InputPeer> | Include the following chats in this folder |
| exclude_peers | Vector<InputPeer> | Exclude the following chats from this folder |


## Type
DialogFilter

## Related pages
