# Mentions

Telegram allows mentioning other users in case of urgent duckling matters, and quickly navigating to those mentions in order to read them as swiftly as possible.

Mentions are implemented as message entities, passed to the messages.sendMessage method:

- inputMessageEntityMentionName - Used when sending messages, allows mentioning a user inline, even for users that don't have a @username

- messageEntityMentionName - Incoming message counterpart of inputMessageEntityMentionName

- messageEntityMention - @botfather (this entity is generated automatically server-side for @usernames in messages, no need to provide it manually)

Incoming messages mentioning to the current user will have the mentioned flag set, and will contain one or more messageEntityMention and messageEntityMentionName constructors.

Graphical clients can show a list of mentionable users when the user starts entering an @ in the text bar; for this purpose, the channelParticipantsMentions filter can be used in channels.getParticipants.
This filter can be enhanced by providing an additional query string q (anything the user enters after @); it will also return non-participant users, in case of channel users commenting in post comment sections.

### Dialog mentions

Graphical clients are supposed to show a blue mention indicator next to the message counter of chats in the dialog list.
The dialog constructor contains an unread_mentions_count field to isolate chats with unread mentions; the actual mention counter should be shown inside of the chat itself, above an @ button that can be used, by clicking multiple times, to navigate back (using messages.getUnreadMentions) through the mention history.

When the last unread mention is read, or when long-clicking on the @ button, all mentions for a chat should marked as read using messages.readMentions.

