# DialogFilter
Dialog filter (folder »)

```
dialogFilter#7438f7e8 flags:# contacts:flags.0?true non_contacts:flags.1?true groups:flags.2?true broadcasts:flags.3?true bots:flags.4?true exclude_muted:flags.11?true exclude_read:flags.12?true exclude_archived:flags.13?true id:int title:string emoticon:flags.25?string pinned_peers:Vector<InputPeer> include_peers:Vector<InputPeer> exclude_peers:Vector<InputPeer> = DialogFilter;
dialogFilterDefault#363293ae = DialogFilter;
dialogFilterChatlist#d64a04a8 flags:# has_my_invites:flags.26?true id:int title:string emoticon:flags.25?string pinned_peers:Vector<InputPeer> include_peers:Vector<InputPeer> = DialogFilter;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| dialogFilter | Dialog filter AKA folder |
| dialogFilterDefault | Used only when reordering folders to indicate the default (all chats) folder. |
| dialogFilterChatlist | A folder imported using a chat folder deep link ». |


## Methods
| Method | Description |
| ---- | ----------- |


