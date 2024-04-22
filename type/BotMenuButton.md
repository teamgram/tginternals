# BotMenuButton
Indicates the action to execute when pressing the in-UI menu button for bots

```
botMenuButtonDefault#7533a588 = BotMenuButton;
botMenuButtonCommands#4258c205 = BotMenuButton;
botMenuButton#c7b57ce6 text:string url:string = BotMenuButton;

---functions---

bots.getBotMenuButton#9c60eb28 user_id:InputUser = BotMenuButton;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| botMenuButtonDefault | Placeholder bot menu button never returned to users: see the docs for more info. |
| botMenuButtonCommands | Bot menu button that opens the bot command list when clicked. |
| botMenuButton | Bot menu button that opens a web app when clicked. |


## Methods
| Method | Description |
| ---- | ----------- |
| bots.getBotMenuButton | Gets the menu button action for a given user or for all users, previously set using bots.setBotMenuButton; users can see this information in the botInfo constructor. |


