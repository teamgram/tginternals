# dialogFilterChatlist
A folder imported using a chat folder deep link ».

```
dialogFilterChatlist#d64a04a8 flags:# has_my_invites:flags.26?true id:int title:string emoticon:flags.25?string pinned_peers:Vector<InputPeer> include_peers:Vector<InputPeer> = DialogFilter;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_my_invites | flags.26?true | Whether the current user has created some chat folder deep links » to share the folder as well. |
| id | int | ID of the folder |
| title | string | Name of the folder |
| emoticon | flags.25?string | Emoji to use as icon for the folder. |
| pinned_peers | Vector<InputPeer> | Pinned chats, folders can have unlimited pinned chats |
| include_peers | Vector<InputPeer> | Chats to include in the folder |


## Type
DialogFilter

## Related pages
