# Admin, banned, default rights
Channels and supergroups allow setting granular permissions both for admins and specific users.
Channels, supergroups and basic groups also allow setting global granular permissions for users.
They can be modified as follows:
### Admin rights
channels.editAdmin can be used to modify the admin rights of a user in a channel or supergroup.
Basic groups do not allow setting granular admin permissions, messages.editChatAdmin has to be used, instead.
Permissions are defined by the chatAdminRights constructor, some admin rights can only be used for channels, others both for channels and supergroups (see the constructor page).
### Banned rights
channels.editBanned can be used to modify the rights of a user in a channel or supergroup, to ban/kick a user from the group, or restrict the user from doing certain things.
Basic groups do not allow setting granular user permissions for single users, single users can only be removed from groups using messages.deleteChatUser: however, setting global granular permissions with basic groups is supported.
Permissions are defined by the chatBannedRights constructor, for more info see the constructor page.
### Default rights
messages.editChatDefaultBannedRights can be used to modify the rights of all users in a channel, supergroup or basic group, to restrict them from doing certain things.
Permissions are defined by the chatBannedRights constructor: all flags can be used except for view_messages, for more info see the constructor page.
### Suggested bot rights
Bots can suggest a set of admin rights when being added to groups and channels.
Bots can use bots.setBotBroadcastDefaultAdminRights to indicate a suggested set of admin rights » to use when adding the bot to a channel, and bots.setBotGroupDefaultAdminRights when adding the bot to a group.
These suggested admin rights are contained in the bot_broadcast_admin_rights and bot_group_admin_rights paremeters of userFull, obtainable using users.getFullUser.
A client application trying to add a bot as admin should fetch the default rights and present them as editable defaults to the user: the rights can then be modified before setting the bot as admin.
Note that admin rights suggested by a bot deep link take priority over the suggested rights specified by bot_broadcast_admin_rights and bot_group_admin_rights: they can still be modified by the user before setting the bot as admin.
