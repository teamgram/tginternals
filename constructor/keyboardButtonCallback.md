# keyboardButtonCallback
Callback button

```
keyboardButtonCallback#35bbdb6b flags:# requires_password:flags.0?true text:string data:bytes = KeyboardButton;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| requires_password | flags.0?true | Whether the user should verify his identity by entering his 2FA SRP parameters to the messages.getBotCallbackAnswer method. NOTE: telegram and the bot WILL NOT have access to the plaintext password, thanks to SRP. This button is mainly used by the official @botfather bot, for verifying the user's identity before transferring ownership of a bot to another user. |
| text | string | Button text |
| data | bytes | Callback data |


## Type
KeyboardButton

## Related pages
