# BotCommandScope
Represents a scope where the bot commands, specified using bots.setBotCommands will be valid.

```
botCommandScopeDefault#2f6cb2ab = BotCommandScope;
botCommandScopeUsers#3c4f04d8 = BotCommandScope;
botCommandScopeChats#6fe1a881 = BotCommandScope;
botCommandScopeChatAdmins#b9aa606a = BotCommandScope;
botCommandScopePeer#db9d897d peer:InputPeer = BotCommandScope;
botCommandScopePeerAdmins#3fd863d1 peer:InputPeer = BotCommandScope;
botCommandScopePeerUser#a1321f3 peer:InputPeer user_id:InputUser = BotCommandScope;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| botCommandScopeDefault | The commands will be valid in all dialogs |
| botCommandScopeUsers | The specified bot commands will only be valid in all private chats with users. |
| botCommandScopeChats | The specified bot commands will be valid in all groups and supergroups. |
| botCommandScopeChatAdmins | The specified bot commands will be valid only for chat administrators, in all groups and supergroups. |
| botCommandScopePeer | The specified bot commands will be valid only in a specific dialog. |
| botCommandScopePeerAdmins | The specified bot commands will be valid for all admins of the specified group or supergroup. |
| botCommandScopePeerUser | The specified bot commands will be valid only for a specific user in the specified group or supergroup. |


## Methods
| Method | Description |
| ---- | ----------- |


