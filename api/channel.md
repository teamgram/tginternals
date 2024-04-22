# Channels, supergroups, gigagroups and basic groups

### Channels

Channels are a tool for broadcasting your messages to large audiences. They can have an unlimited number of subscribers, they can be public with a permanent URL and each post in a channel has its own view counter.
Technically, they are represented by channel constructors.

Channels can be created using the channels.createChannel method, by setting the broadcast flag.

### Supergroups

Supergroups are a powerful tool for building communities and can support up to 200,000 members each.
Technically, supergroups are actually channels: they are represented by channel constructors, with the megagroup flag set to true.

Channels can be created using the channels.createChannel method, by setting the megagroup flag.
Supergroups can also be assigned a geo_point to become geochats ».

#### Forums

Supergroups can be converted into forums, splitting conversion into distinct forum topics, see the forum documentation for more info ».

### Gigagroups

Gigagroups are something between a channel and a supergroup.
An admin, when prompted by the API using suggestions », can convert a megagroup into a gigagroup using channels.convertToGigagroup (one way only).
After that, only admins will be able to write in the group (like when send_messages rights are disabled for all group participants by default), but the participant limit is removed and the group can become much bigger than a supergroup (e.g. >200,000 currently).
Also, one can't invite people into gigagroups and participants of voice chats in gigagroups are muted by default.

### Basic groups

In previous versions of telegram, only basic groups (represented by chat constructors) could be created using messages.createChat: these groups have fewer features, and can only have 200 members at max.
Messages from all basic groups are stored in the user's message box »: this means that all basic groups and all private chats share the same, single message ID and PTS sequence.

#### Migration

To upgrade a basic group to a supergroup, messages.migrateChat can be used.
The chats field of the result will have two objects:

- A chat constructor with a migrated_to field, indicating the address of the new supergroup

- The new channel megagroup constructor

When getting full info about the migrated channel, the channelFull object will have migrated_from_chat_id and migrated_from_max_id fields indicating the original ID of the chat, and the message ID in the original chat at which the group was migrated.

All users of the chat will receive an updateNewMessage from the old chat with a messageService containing a messageActionChatMigrateTo constructor.

All new messages have to be sent to the new supergroup.

When working with migrated groups clients need to handle loading of the message history (as well as search results et cetera) from both the basic group and the new supergroup. This is done by merging the two messages lists (requested with different Peer values) client side.

### Invite links and join requests

Channels, basic groups and supergroups may have a public username or a private invite link: private invite links may be further enhanced with per-user join requests.

For more info on how to work with public usernames, invite links and join requests, see here ».

### Rights

Channels, basic groups and supergroups allow setting granular permissions both for admins and specific users; channels, supergroups and basic groups also allow setting global granular permissions for users.

For more info on how to set and modify rights, see here ».

### Pinned messages

Telegram allows pinning multiple messages on top in a chat, group, supergroup or channel.

See here » for more info on pinning and unpinning messages.

### Discussion

Groups can be associated to a channel as a discussion group, to allow users to discuss about posts.

For more info on how to set a discussion group in channel, see here »

### Recent actions

Both supergroups and channels offer a so-called admin log, a log of recent relevant supergroup and channel actions, like the modification of group/channel settings or information on behalf of an admin, user kicks and bans, and more.

See here » for more info.

