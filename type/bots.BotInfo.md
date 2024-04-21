# bots.BotInfo
Localized name, about text and description of a bot.

```
bots.botInfo#e8a775b0 name:string about:string description:string = bots.BotInfo;

---functions---

bots.getBotInfo#dcd914fd flags:# bot:flags.0?InputUser lang_code:string = bots.BotInfo;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| bots.botInfo | Localized information about a bot. |


## Methods
| Method | Description |
| ---- | ----------- |
| bots.getBotInfo | Get localized name, about text and description of a bot (or of the current account, if called by a bot). |


