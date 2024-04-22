# Saved messages
The Saved Messages chat allows users to bookmark messages and media: it's a personal cloud storage for any messages or media you may want to send or forward there.
Internally, the Saved Messages chat is simply the private chat with ourselves (i.e. the chat with inputPeerSelf): the only difference between the Saved Messages chat and a chat with any other user, is that additional features are available to better organize messages and media sent to it.
Schema:
Messages sent and forwarded from various users (including ourselves) to Saved Messages are automatically categorized by their original dialog into a saved dialog list, quite similar to the normal dialog list used to normally interact with chats.
To add new dialogs to the normal dialog list a user has to write to them (or join a channel/chat, etc.).
To add new dialogs to the saved dialog list, simply forward messages from any normal dialog to inputPeerSelf (the current user): the forwarded messages (including outgoing ones) will be added to a saved dialog with the same ID of the original dialog.
This includes outgoing messages, for example assume the following:
- Our user id is equal to 11111111
- We send a message A with ID 10 to a supergroup with id=-100122222222 (bot API format, equivalent to a peerChannel with ID 122222222)
- Another user with id=133333333 replies B to our previous message, message ID 11
- We forward both messages A and B with IDs 10 and 11 to inputPeerSelf, which will:
- Create a new savedDialog with peer=-100122222222 (if it doesn't exist already because we already forwarded messages from that supergroup)
- Generate two messages:
- Message A:
- id: an unrelated message ID, the next one in the common ID sequence, for example 1234
- peer_id: 11111111
- saved_peer_id: -100122222222
- fwd_from.from_id: 11111111
- fwd_from.saved_from_peer: -100122222222
- fwd_from.saved_from_msg_id: 10
- Message B:
- id: an unrelated message ID, the next one in the common ID sequence, for example 1235
- reply_to.reply_to_msg_id: 1234
- peer_id: 11111111
- saved_peer_id: -100122222222
- fwd_from.from_id: 133333333
- fwd_from.saved_from_peer: -100122222222
- fwd_from.saved_from_msg_id: 11
Saving messages from private chats with users with forward privacy enabled will add them to a saved dialog entry of a special anonymous user with id=2666000.
Clients may use the following pseudocode to manually populate the saved_peer_id of old layer < 170 messages stored in the local database.
Sending (not forwarding from another dialog) new messages directly to ourselves will add them to a saved dialog entry with ourselves.
A set of methods can then be used to obtain this dialog list, pin/unpin dialogs inside of it, view and remove messages from saved dialogs: messages.getSavedDialogs, messages.getSavedHistory, messages.deleteSavedHistory, messages.getPinnedSavedDialogs, messages.toggleSavedDialogPin, messages.reorderPinnedSavedDialogs work just like their counterparts messages.getDialogs, messages.getHistory, messages.deleteHistory, messages.getPinnedDialogs, messages.toggleDialogPin, messages.reorderPinnedDialogs, with the sole difference that they affect the saved dialog list, instead of the main dialog list.
To search for messages within a saved dialog, use the usual messages.search, messages.getSearchCounters, messages.getSearchResultsCalendar, messages.getSearchResultsPositions methods with peer=inputPeerSelf and saved_peer_id=id of the saved dialog.
