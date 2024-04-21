# messageActionSetChatWallPaper
The wallpaper » of the current chat was changed.

```
messageActionSetChatWallPaper#5060a3f4 flags:# same:flags.0?true for_both:flags.1?true wallpaper:WallPaper = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| same | flags.0?true | If set, indicates the user applied a wallpaper » previously sent by the other user in a messageActionSetChatWallPaper message. |
| for_both | flags.1?true | If set, indicates the wallpaper was forcefully applied for both sides, without explicit confirmation from the other side. If the message is incoming, and we did not like the new wallpaper the other user has chosen for us, we can re-set our previous wallpaper just on our side, by invoking messages.setChatWallPaper, providing only the revert flag (and obviously the peer parameter). |
| wallpaper | WallPaper | New wallpaper |


## Type
MessageAction

## Related pages
