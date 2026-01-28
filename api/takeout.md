# Takeout API

Telegram's API allows users to export all of their information through the takeout API.

```
account.takeout#4dba4501 id:long = account.Takeout;

inputTakeoutFileLocation#29be5899 = InputFileLocation;

---functions---

account.initTakeoutSession#8ef3eab0 flags:# contacts:flags.0?true message_users:flags.1?true message_chats:flags.2?true message_megagroups:flags.3?true message_channels:flags.4?true files:flags.5?true file_max_size:flags.5?long = account.Takeout;

invokeWithTakeout#aca9fd2e {X:Type} takeout_id:long query:!X = X;

account.finishTakeoutSession#1d2652ee flags:# success:flags.0?true = Bool;
```

Use account.initTakeoutSession to initialize a takeout session: pass the appropriate flags to enable usage of the corresponding methods, as described below.

When invoking the methods described below, each query must be wrapped using invokeWithTakeout, with the id returned by account.initTakeoutSession.

After finishing the export, terminate the session using account.finishTakeoutSession.

### Split ranges

```
messageRange#ae30253 min_id:int max_id:int = MessageRange;

---functions---

messages.getSplitRanges#1cff7e08 = Vector<MessageRange>;

invokeWithMessagesRange#365275f2 {X:Type} range:MessageRange query:!X = X;
```

Some method calls require additional pagination using message ranges.

First of all, obtain a list of message ranges by invoking messages.getSplitRanges (wrapping it in an invokeWithTakeout as usual).

Then, when invoking methods that require message range pagination, wrap the method using invokeWithMessagesRange, before also wrapping it in an invokeWithTakeout as usual.

Start by passing the first message range; continue passing the same message range while paginating using the usual offset_*, limit, etc parameters; once there are no more results left, switch to the next message range, re-starting offset_*, limit pagination from the beginning.
Repeat until you've finished all the message ranges that were returned by messages.getSplitRanges.

### Procedure

Example implementation: tdesktop.

Here's an overview of the steps required to export account information.

All requests must be wrapped in an invokeWithTakeout constructors, including upload.getFile calls to save files.

Unless otherwise specified, all requests do not require pagination using split ranges.

- If the user wants to download messages from chats, groups or channels:

- First of all, fetch and save the dialog list using split ranges and messages.getDialogs; at the beginning of each split range, make an initial request with all offsets set to 0 and limit=1 to fetch total dialog count to display a proper progress bar.

- Request and save info about left channels and supergroups if the user wants to export channel and group messages.

- For all dialogs, check if they match the dialog types chosen by the user, and if yes download all messages using split ranges and messages.getHistory; for each split range, make an initial request with all offsets set to 0 and limit=1 to fetch the initial message count to display a proper progress bar.

- Use the single message returned by the initial limit=1 request to also skip ranges that don't have any messages, because an empty messages vector or a single messageEmpty is returned.

- If the user also chose to download only messages within a specific date interval, skip ranges whose:

- Last message (returned by that same initial limit=1 call) has a date bigger than the top of the specified date interval.

- First message (returned by a new call to messages.getHistory with limit=1, offset_id=1, add_offset=-1) has a date smaller than the bottom of the specified date interval.

- For each downloaded and saved message, also download and save all attached media, including custom emojis present in messages and captions, respecting the per-file download filesize limits imposed by the user.

- If the user chose to download only their own messages, not messages sent by other users, use messages.search with peer set to inputPeerSelf instead of messages.getHistory.

- If the user wants to export their stories:

- Use stories.getStoriesArchive to fetch, download and store all posted stories, including custom emojis present in captions.

- If the user wants to export personal info:

- Invoke and store the result of users.getFullUser with inputUserSelf.

- If the user wants to export their own profile pictures:

- Invoke photos.getUserPhotos to fetch the list of and download all profile pictures.

- If the user wants to export their contact list:

- See here »

- If the user wants to export their sessions:

- Invoke and store the result of account.getAuthorizations and account.getWebAuthorizations

- If the user wants to export any other data not mentioned above, like for example personal data related to new Telegram features, that do not have any specific takeout methods in the Takeout API yet.

- Use upload.getFile with inputTakeoutFileLocation; this will download a JSON file that will contain all personal data related to features that do not have a specialized takeout method yet.

#### Contacts

```
savedPhoneContact#1142bd56 phone:string first_name:string last_name:string date:int = SavedContact;

---functions---

contacts.getSaved#82f1e39f = Vector<SavedContact>;
```

This method does not require pagination using message ranges.

Use contacts.getSaved to export the full contact list, see here » for another alternative method that may be used to fetch the full list of all contacts with a Telegram account, without using a takeout session.

#### Left channels

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;

---functions---

channels.getLeftChannels#8341ecc0 offset:int = messages.Chats;
```

This method does not require pagination using message ranges.

Use channels.getLeftChannels to get a list of channels or supergroups we left.

