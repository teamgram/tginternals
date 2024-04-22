# Wallpapers
Telegram apps support generating, sharing and synchronizing chat backgrounds.
Wallpapers must be rendered according to the instructions contained in the wallpaper constructors.
### Wallpaper types
There are four main wallpaper types:
- Image wallpapers
- Pattern wallpapers
- Fill wallpapers
- Channel wallpapers
Fill and pattern wallpapers are generated using one of three fill types.
#### Image wallpapers
Image wallpapers are wallpapers described by a wallPaper constructor, containing a JPEG image in the document field.
The settings field describes the transforms that should be applied to the image if the corresponding flags are set:
- settings.blur: The image should be downscaled to fit in 450x450 square and then box-blurred with radius 12.
- settings.motion: The image needs to be slightly moved when device is tilted, allowing for a parallax effect.
All other settings flags should be ignored.
#### Pattern wallpapers
Pattern wallpapers are wallpapers described by a wallPaper constructor with the pattern flag set, combining the color fill specified by the settings field with the PNG or TGV (gzipped subset of SVG with MIME type "application/x-tgwallpattern") pattern image contained in the document field.
The pattern image should be completely transparent, except for the pattern itself which should be shades of black.
The following flags in the settings field describe how should the pattern be combined with the color fill:
- settings.intensity: A value ranging from -100 to 100.
- Values from 0 to 100 mean that the pattern should be overlaid on top of the color fill with the specified intensity (@ 100 the black pattern is fully visible on the background fill, @ 0 only the background fill is visible).
- Values from -1 to -100 mean that the pattern should be inverted (black background, transparent pattern) before overlaying on top of the color fill with the specified intensity (@ -100 the filled pattern is fully visible on a black background, @ -1 only black is visible).
- settings.motion: The pattern needs to be slightly moved on top of the background when device is tilted, allowing for a parallax effect.
#### Fill wallpapers
Fill wallpapers are simple wallpapers described by the wallPaperNoFile constructor, containing only the fill specified by the settings field.
#### Channel wallpapers
Fill wallpapers with an emoticon contained in the associated wallpaper settings indicate a channel wallpaper, that can be installed » in channels that have enough boosts, see here » for more info.
The full list of channel wallpapers can be fetched using account.getChatThemes.
Channels may also set any custom wallpaper (not just the ones returned by account.getChatThemes) after reaching a higher boost level, see here » for more info.
### Fill types
Fill and pattern wallpapers are generated using one of three fill types:
- Solid fill
- Gradient fill
- Freeform gradient fill
#### Solid fill
If out of the *_background_color flags only background_color is set, the fill is made of just the specified RGB-24 color.
#### Gradient fill
If out of the *_background_color flags only background_color and second_background_color are set, the fill is made of a top-bottom (background-second_background) gradient of the specified RGB-24 colors.
If set, rotation indicates clockwise rotation angle of the gradient, in degrees; 0-359. Must be always divisible by 45, default to 0 if not set.
#### Freeform gradient fill
If the background_color, second_background_color, third_background_color and optionally fourth_background_color flags are set, the fill is made of a freeform gradient of the specified 3 or 4 RGB-24 colors.
### Wallpaper API
#### Uploading wallpapers
account.uploadWallPaper is used to upload image and pattern wallpapers. The for_chat flag must be set when uploading wallpapers to be used with messages.setChatWallPaper.
Fill wallpapers don't require uploading since they have no associated file, and a wallPaper constructor can directly be generated client-side, specifying id=0.
Wallpapers can then be shared using a wallpaper deep link », and/or installed as specified here (image and pattern wallpapers only) ».
#### Installing wallpapers
Once you've uploaded your wallpaper or received a wallpaper deep link, it can be installed as follows.
Note that fill wallpapers cannot be globally installed using account.installWallPaper or account.saveWallPaper, clients should install and keep track of them only locally, without synchronizing the wallpaper list or signaling installations.
The API keeps a list of wallpapers that the user can set as chat background, including some preinstalled ones.
To fetch the list use account.getWallPapers.
To save a wallpaper to the list use account.saveWallPaper with unsave=false.
To remove a wallpaper (including preinstalled wallpapers) from the list use account.saveWallPaper with unsave=true.
To restore the default list, removing all installed wallpapers and reinstalling previously removed preinstalled wallpapers use account.resetWallPapers.
When a client sets a wallpaper as the default chat background, call account.installWallPaper to signal this installation to the server.
Note that calling this method will also automatically save the wallpaper, if it's not present in the saved wallpapers list.
In all cases where an InputWallPaper constructor is required, pass:
- inputWallPaperSlug when working with wallpaper deep links.
- inputWallPaper otherwise, using the ID and access hash fields of a full wallPaper.
- As mentioned earlier, fill wallpapers can't be saved to the server using account.installWallPaper or account.saveWallPaper: an inputWallPaperNoFile is available for fill wallpapers but can only be used when working with themes » or when using messages.setChatWallPaper as follows.
#### Installing wallpapers in a specific chat or channel
Wallpapers can also be installed in a specific private chat, by using messages.setChatWallPaper: this will emit a messageActionSetChatWallPaper service message, displaying the wallpaper in the UI along with an invitation for the other user to apply the same wallpaper.
To wallpaper, pass an:
- inputWallPaperSlug when working with wallpaper deep links.
- inputWallPaperNoFile for fill wallpapers.
- inputWallPaper otherwise, using the ID and access hash fields of a full wallPaper.
If the other user decides to apply the same wallpaper to the chat, messages.setChatWallPaper should be invoked passing the wallpaper settings received in the messageActionSetChatWallPaper service message (or some different settings, if the user customized them before applying the wallpaper), along with the id of the messageActionSetChatWallPaper service message, without the wallpaper: this way, the action will emit a messageActionSetChatWallPaper with the same flag set, which should be displayed in the UI as a simple acknowledgment service message, without the full wallpaper and without an invitation for the other user to apply it (since both participants already just did that).
However, if we have Premium subscription, we can change the other user's wallpaper without explicit confirmation from the other side: to do so, set the for_both flag when invoking messages.setChatWallPaper.
This will change the wallpaper for both sides of the chat, without requiring confirmation; the userFull.wallpaper_overridden flag will also be set for the other user; the action will also emit a messageActionSetChatWallPaper with the for_both flag set.
If the other user does not like the new wallpaper we have chosen for them, they can re-set their previous wallpaper just on their side, by invoking messages.setChatWallPaper, providing only the revert flag (and obviously the peer parameter).
Note that in order to pass image or pattern wallpapers to messages.setChatWallPaper, the for_chat flag must be set when uploading them with account.uploadWallPaper.
Also note that unlike account.installWallPaper or account.saveWallPaper, messages.setChatWallPaper accepts fill wallpapers as well.
Wallpaper changes will also emit an updatePeerWallpaper update.
After reaching at least the boost level specified in the channel_wallpaper_level_min config parameter, channels gain the ability to set one of the fill channel wallpapers returned by account.getChatThemes (see » for more info).
After reaching at least the boost level specified in the channel_custom_wallpaper_level_min config parameter, channels gain the ability to set any custom wallpaper, not just fill channel wallpapers.
When setting channel wallpapers, do not set the for_both flag.
