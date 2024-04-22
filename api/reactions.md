# Message reactions
Telegram allows users to react on any message using specific emojis, triggering cute lottie animations.
### React to a message
Users can react to a message with one or more reactions using messages.sendReaction.
After sending the reaction, the chosen_order field of reactionCount will be set for the reaction. The integer value indicates when was the reaction added: the bigger the value, the newer the reaction, use this value to appropriately sort the messages.sendReaction:reaction vector when adding new reactions.
Reactions should be sent in ascending order (new reactions at the end in the messages.sendReaction:reaction vector), and when adding more reactions to the same message, older reactions should be removed to keep the total number of sent reactions within reactions_user_max_default/reactions_user_max_premium reactions.
The reactions_uniq_max configuration field also indicates the maximum number of unique reactions that can be added to a message: for example, if there are 2000  and 1000 custom emoji  reactions and reactions_uniq_max = 2, you can't add a  reaction, because that would raise the number of unique reactions to 3 > 2.
The big flag can be optionally set to elicit a bigger reaction.
Send a reactionEmoji to react using a normal emoji, and a reactionCustomEmoji to react using a custom emoji.
Message authors will receive an updateMessageReactions update when a user reacts to their message.
messages.getMessagesReactions can be used to fetch a full list of reactions for one or more messages.
Apps should short-poll reactions for visible messages (that weren't sent by the user) once every 15-30 seconds, but only if message.reactions is set.
In groups, messages.getMessageReactionsList can be used to fetch the reaction list, along with the sender of each reaction.
In groups, messages.reportReaction can be used to report a certain custom emoji reaction, specifying the peer, the message id and the user that sent the reaction (reaction_peer).
messages.getUnreadReactions is used to fetch messages with unread reactions.
Use messages.readReactions to mark all reactions as read in a certain chat.
### React to a story
See here » for more info on how to react to a story.
### Animated normal emojis
messages.getAvailableReactions can be used to fetch a list of animations to play when reacting with a normal reactionEmoji.
The returned vector of availableReaction constructors contains multiple fields with lottie animated stickers and simple images that should be positioned, displayed and played appropriately in the UI, as described in the constructor page ».
Users can also react using custom emojis », in which case the appear_animation and select_animation are equal to the custom emoji itself that can be fetched as described here ».
For custom emojis, the effect_animation must be equal to the effect_animation of the associated normal emoji: if no effect animation is present for the normal emoji associated to a custom emoji, a random animated sticker should be played from the inputStickerSetEmojiGenericAnimations stickerset, fetched using messages.getStickerSet as described here ».
### Available reactions in group or channel
Chat and channel administrators can use messages.setChatAvailableReactions to restrict the set of reactions that can be used in a chat or channel, see here » for a list of possible configuration values.
The set ChatReactions constructor can then be fetched by users using messages.getFullChat, and will be contained in the available_reactions field of the returned full info constructor.
The reactions_in_chat_max configuration field indicates the maximum number of reactions that can be specified in chatReactionsSome.
### Recent reactions
Recently used reactions can be fetched using messages.getRecentReactions: the list can be cleared using messages.clearRecentReactions.
The add_to_recent flag of messages.sendReaction must be set iff the user reacts to a message using the extended reactions menu (as opposed to the reaction bubble): this will update the recent reaction list, triggering an updateRecentReactions update on other logged-in sessions: this update should trigger a new call to messages.getRecentReactions to refresh the locally cached list.
### Featured reactions
A list of featured emoji and custom emoji reactions can be fetched using messages.getTopReactions.
### Set default reaction
messages.setDefaultReaction can be used to change the default emoji reaction to use in the quick reaction menu.
This value is synced across devices and can be fetched using help.getConfig, reactions_default field.
