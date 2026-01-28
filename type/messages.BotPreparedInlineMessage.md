# Messages.BotPreparedInlineMessage
Represents a prepared inline message saved by a bot, to be sent to the user via a web app »

```
messages.botPreparedInlineMessage#8ecf0511 id:string expire_date:int = messages.BotPreparedInlineMessage;

---functions---

messages.savePreparedInlineMessage#f21f7f2f flags:# result:InputBotInlineResult user_id:InputUser peer_types:flags.0?Vector<InlineQueryPeerType> = messages.BotPreparedInlineMessage;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.botPreparedInlineMessage | Represents a prepared inline message saved by a bot, to be sent to the user via a web app » |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.savePreparedInlineMessage | Save a prepared inline message, to be shared by the user of the mini app using a web_app_send_prepared_message event |


