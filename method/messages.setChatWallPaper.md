# messages.setChatWallPaper
Set a custom wallpaper » in a specific private chat with another user.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.setChatWallPaper#8ffacae1 flags:# for_both:flags.3?true revert:flags.4?true peer:InputPeer wallpaper:flags.0?InputWallPaper settings:flags.2?WallPaperSettings id:flags.1?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| for_both | flags.3?true | Only for Premium users, sets the specified wallpaper for both users of the chat, without requiring confirmation from the other user. |
| revert | flags.4?true | If we don't like the new wallpaper the other user of the chat has chosen for us using the for_both flag, we can re-set our previous wallpaper just on our side using this flag. |
| peer | InputPeer | The private chat where the wallpaper will be set |
| wallpaper | flags.0?InputWallPaper | The wallpaper », obtained as described in the wallpaper documentation »; must not be provided when installing a wallpaper obtained from a messageActionSetChatWallPaper service message (id must be provided, instead). |
| settings | flags.2?WallPaperSettings | Wallpaper settings, obtained as described in the wallpaper documentation » or from messageActionSetChatWallPaper.wallpaper.settings. |
| id | flags.1?int | If the wallpaper was obtained from a messageActionSetChatWallPaper service message, must contain the ID of that message. |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | WALLPAPER_INVALID | The specified wallpaper is invalid. |
| 400 | WALLPAPER_NOT_FOUND | The specified wallpaper could not be found. |

