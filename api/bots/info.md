# Edit bot information

Users can edit and localize the profile picture, name, about text and description of bots they own; the same can be done by the bots themselves.

Bots may invoke bots.setBotInfo set a localized version of their name, about text and description; bots.getBotInfo may be used to obtain previously set values.
Bots may also invoke photos.uploadProfilePhoto as specified in the files documentation » to set profile photos, videos or stickers.

The same methods may be invoked by the user that owns the bot (bots owned by the current user have the user.bot_can_edit flag set) to modify the bot's information: to do so, specify the bot's peer information in the bot parameter.

