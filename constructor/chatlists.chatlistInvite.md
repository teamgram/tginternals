# chatlists.chatlistInvite
Info about a chat folder deep link ».

```
chatlists.chatlistInvite#f10ece2f flags:# title_noanimate:flags.1?true title:TextWithEntities emoticon:flags.0?string peers:Vector<Peer> chats:Vector<Chat> users:Vector<User> = chatlists.ChatlistInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| title_noanimate | flags.1?true | If set, any animated emojis present in title should not be animated and should be instead frozen on the first frame. |
| title | TextWithEntities | Name of the link |
| emoticon | flags.0?string | Emoji to use as icon for the folder. |
| peers | Vector<Peer> | Supergroups and channels to join |
| chats | Vector<Chat> | Related chat information |
| users | Vector<User> | Related user information |


## Type
chatlists.ChatlistInvite

## Related pages
