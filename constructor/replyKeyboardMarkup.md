# replyKeyboardMarkup
Bot keyboard

```
replyKeyboardMarkup#85dd99d1 flags:# resize:flags.0?true single_use:flags.1?true selective:flags.2?true persistent:flags.4?true rows:Vector<KeyboardButtonRow> placeholder:flags.3?string = ReplyMarkup;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| resize | flags.0?true | Requests clients to resize the keyboard vertically for optimal fit (e.g., make the keyboard smaller if there are just two rows of buttons). If not set, the custom keyboard is always of the same height as the app's standard keyboard. |
| single_use | flags.1?true | Requests clients to hide the keyboard as soon as it's been used. The keyboard will still be available, but clients will automatically display the usual letter-keyboard in the chat – the user can press a special button in the input field to see the custom keyboard again. |
| selective | flags.2?true | Use this parameter if you want to show the keyboard to specific users only. Targets: 1) users that are @mentioned in the text of the Message object; 2) if the bot's message is a reply (has reply_to_message_id), sender of the original message.Example: A user requests to change the bot's language, bot replies to the request with a keyboard to select the new language. Other users in the group don't see the keyboard. |
| persistent | flags.4?true | Requests clients to always show the keyboard when the regular keyboard is hidden. |
| rows | Vector<KeyboardButtonRow> | Button row |
| placeholder | flags.3?string | The placeholder to be shown in the input field when the keyboard is active; 1-64 characters. |


## Type
ReplyMarkup

## Related pages
