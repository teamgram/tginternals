# Accent colors
Telegram users and channels can change the accent color and background pattern of their profile page and their messages!
Schema:
A peerColor constructor contains a color palette ID (id) and a custom emoji sticker » (background_emoji) to be re-colored using the colors in the palette and spread out throughout the palette, generating a background that can be used in the profile page of a user, and in other places throughout the UI, namely in in webpage preview message frames and message accent colors when quoting or replying to messages sent by a channel or user that enabled a custom message accents.
The color palettes is identified by an id (not by an RGB24 color); use help.getPeerProfileColors to obtain all color palettes (represented by help.peerColorOption constructors) that can be used in the background of a profile page, and use help.getPeerColors to obtain all color palettes that can be used in message accents.
A color palette is represented by a help.peerColorOption constructor: the palette ID is contained in color_id; the palette for light mode is contained in the colors field, the palette for dark mode is contained in the dark_colors field.
If the hidden flag is set it should not be displayed as an option to the user when choosing a palette to use in the profile page or in message accents.
The actual colors that should be used are contained either in a help.peerColorSet (returned by help.getPeerColors, containing a palette for message accents) or in a help.peerColorProfileSet (returned by help.getPeerColors containing a palette for profile pages), see the relative constructor pages for more info.
Use account.getDefaultBackgroundEmojis to obtain a list of IDs of custom emojis that can be used in a palette background.
All custom emojis in custom emoji stickersets » with text_color flag set can also be used for the same purpose.
Use account.updateColor to update the color palette of the current account's message accents and/or profile page; note that the current account must be subscribed to Telegram Premium in order to call the method.
Use channels.updateColor to update the color palette of the channel's message/profile page accents.
Note that channels can use a message accent palette or profile palette only after reaching at least the boost level specified in the channel_min_level field of the help.peerColorOption constructor for the chosen palette.
Additionally, to change profile palettes, channels must also reach at least the boost level specified in the channel_profile_bg_icon_level_min config parameter.
The chosen message accent palette will be visible to other users in the channel.color and user.color fields.
The chosen user and channel profile palettes will be visible in the user.profile_color and channel.profile_color fields.
