# account.updateConnectedBot
Connect a business bot » to the current account, or to change the current connection settings.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
account.updateConnectedBot#66a08c7e flags:# deleted:flags.1?true rights:flags.0?BusinessBotRights bot:InputUser recipients:InputBusinessBotRecipients = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| deleted | flags.1?true | Whether to fully disconnect the bot from the current account. |
| rights | flags.0?BusinessBotRights | Business bot rights. |
| bot | InputUser | The bot to connect or disconnect |
| recipients | InputBusinessBotRecipients | Configuration for the business connection |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_BUSINESS_MISSING | The specified bot is not a business bot (the user.bot_business flag is not set). |
| 400 | BUSINESS_RECIPIENTS_EMPTY | You didn't set any flag in inputBusinessBotRecipients, thus the bot cannot work with any peer. |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |

