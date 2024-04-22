# Dice
On startup, clients should fetch app configuration using help.getAppConfig.
Then, for each dice emoji contained in the emojies_send_dice field, clients should fetch the dice emoji stickerset by calling the messages.getStickerSet method, providing the properly populated inputStickerSetDice to the stickerset field.
The returned stickerset will contain a set of animated stickers, one for each of the dice outcomes, plus a first looping sticker that should be shown as preview to the user before actually sending the dice.
If a user attempts to send a single emoji from the ones specified in emojies_send_dice, the dice should be sent using messages.sendMedia, providing the dice emoji to the emoticon field.
Incoming dice stickers will be received as a messageMediaDice constructor, along with a randomly generated server-side value, ranging from 1 to the maximum allowed value for this type of dice.
Clients should display the correct dice animated sticker for the specified value: since dice values start from 1, and the first animated sticker in dice stickerset is the preview, value can be used to directly index the documents sticker array from the animated stickerset.
The emojies_send_dice_success configuration parameter contains more info about dice emojis other than the basic :
For each of the dice emojis, a maximum "winning" value is specified, along with the frame number at which to show the fireworks .
Please note that dice animated stickers should loop only once, right after being sent/received for the first time; clicking on the dice sticker should bring up a popup, inviting the user to send a new dice of the same type.
### Slot machine
Slot machine  dice stickers are implemented a bit differently: the value isn't used to directly index the stickers array, but is instead used as follows.
The value is composed of three 2-bit values, each indicating the animated sticker to show in the three slots, incremented by one.
The stickers array is composed as follows:
- 0 => Slot machine background
- 1 => Slot machine winning background, to show after a winning spin
- 2 => Slot machine frame&handle to play once at the beginning
- 3 => Left slot winning 7
- 4..7 => Left slot non-winning options
- 8 => Left slot spinning animation
- 9 => Center slot winning 7
- 10..13 => Center slot non-winning options
- 14 => Center slot spinning animation
- 15 => Right slot winning 7
- 16..19 => Right slot non-winning options
- 20 => Right slot spinning animation
How to play the animation (all involved stickers are to be directly overlaid on top of each other, no special placing is required):
- Freeze single-frame background (0)
- Play handle animation (2) once
- Play the three spinning slots animations (8, 14, 20) once
- Play the three slot animations once, chosen as follows:
- If we're in a winning value == 64:
- Left slot: choose 3
- Center slot: choose 9
- Right slot: choose 15
- Otherwise, considering map := [1, 2, 3, 0]:
- Left slot: choose 4 + map[(value-1) & 3]
- Center slot: choose 10 + map[((value-1) >> 2) & 3]
- Right slot: choose 16 + map[((value-1) >> 4) & 3]
- If we're in a winning value=64, replace the background (0) with 1.
Example implementation: tdesktop.
