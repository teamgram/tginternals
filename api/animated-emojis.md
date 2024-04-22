# Animated Emojis
Graphical telegram clients should transform emojis into their respective animated version.
### Animated emojis
On startup, clients should fetch the animated emoji stickerset by calling the messages.getStickerSet method, providing inputStickerSetAnimatedEmoji to the stickerset field.
The returned stickerset will contain a set of animated stickers, one for each of the supported emojis.
Clients should substitute messages containing only one instance of one of the allowed emojis with the respective animated sticker.
Also, when receiving messages containing only one instance of a custom emoji, instead of displaying a message bubble with a single small custom emoji inside, the scaled-up custom emoji should be displayed directly, like with normal stickers.
Animated emojis should loop only once when first sent or received, or when clicked.
For supported emojis, clients on both sides of private chats with users are supposed to show a reaction animation when any of the two users clicks on the animated emoji: click here for more info ».
For special dice emojis like , , or , clients are supposed to behave differently both when sending and receiving such emojis: click here for more info ».
### Emojis with sounds
Certain animated emojis should play sound when clicked, as specified by server-side configuration.
The returned JSON object will contain the following map, with a list of file IDs to download:
The file reference field should be base64-decoded before downloading the file.
### Emoji reactions
Not to be confused with message reactions ».
On startup, clients should fetch the animated reaction emoji stickerset by calling the messages.getStickerSet method, providing inputStickerSetAnimatedEmojiAnimations to the stickerset field.
The returned stickerset will contain a set of animated emoji reactions, one or more for each of the supported emojis.
If a set of reactions for the  emoji is returned, the same reactions should also be assigned to the , , , , , ,  and  emojis.
Clients on both sides of private chats with users should overlay one of the appropriate reaction animations over the animated sticker when any of the two users clicks on a supported animated emoji.
The same should happen for standalone custom emojis (single custom emojis are always displayed as standalone stickers) if the underlying normal emoji is supported (as above).
The reaction animation for each separate tap should be chosen randomly from all the available reactions for a given emoji, and multiple taps should be aggregated and sent to the other user as follows:
At each tap, clients should store all occurred taps in a local list.
After 1 second has elapsed with no more taps, the local list should be cleared and stored taps should be sent using messages.setTyping, passing a sendMessageEmojiInteraction constructor with the following fields:
- emoticon - The emoji we're reacting to
- msg_id - Message ID of the animated emoji that was clicked
- interaction - A JSON object with interaction info, containing the following keys:
- v - An integer indicating the object version, currently 1
- a - An array of JSON objects, each containing the following keys:
- t - float, number of seconds that passed since the previous tap in the array, the first tap uses a value of 0.0.
- i - integer, 1-based index of the randomly chosen animation for the tap (equivalent to the index of a specific emoji-related animation in stickerPack + 1).
1 second after the receiving user has seen the last reaction animation for a specific emoji, an acknowledgement must be sent using messages.setTyping, passing a sendMessageEmojiInteractionSeen with that emoji.
