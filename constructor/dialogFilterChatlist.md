# dialogFilterChatlist
A folder imported using a chat folder deep link ».

```
dialogFilterChatlist#96537bd7 flags:# has_my_invites:flags.26?true title_noanimate:flags.28?true id:int title:TextWithEntities emoticon:flags.25?string color:flags.27?int pinned_peers:Vector<InputPeer> include_peers:Vector<InputPeer> = DialogFilter;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_my_invites | flags.26?true | Whether the current user has created some chat folder deep links » to share the folder as well. |
| title_noanimate | flags.28?true | If set, any animated emojis present in title should not be animated and should be instead frozen on the first frame. |
| id | int | ID of the folder |
| title | TextWithEntities | Name of the folder (max 12 UTF-8 chars) |
| emoticon | flags.25?string | Emoji to use as icon for the folder. |
| color | flags.27?int | A color ID for the folder tag associated to this folder, see here » for more info. |
| pinned_peers | Vector<InputPeer> | Pinned chats, folders can have unlimited pinned chats |
| include_peers | Vector<InputPeer> | Chats to include in the folder |


## Type
DialogFilter

## Related pages
