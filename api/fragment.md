# Collectible usernames

Telegram users can make it easy for others to contact them or find their public groups and channels via usernames: clients can also assign multiple collectible usernames to accounts, supergroups and channels they own.

Schema:

Collectible usernames work just like basic @usernames, they appear in Global Search results and have deep links », just like basic usernames.

The ownership of collectible usernames is secured by TON, a fast and scalable blockchain network. They can be bought and sold through the Fragment platform », giving a simple and secure way to acquire and exchange valuable Telegram domains.

On the Fragment platform, clients may associate or dissociate purchased collectible usernames either to their Telegram account, or to a bot/channel/supergroup they own.

If any collectible username is associated to an account, channel or supergroup, user.username and channel.username won't be set, and user.usernames and channel.usernames will be set, instead: these fields contain an array of username constructors, which indicate whether a certain username is a basic username (editable is set) or a collectible username (editable is not set); and whether a collectible username is active or not.
The first username in the usernames vector must be shown in-UI as the main username.

Immediately after association, a username is marked as not active (i.e. only the owner can see it in the usernames list): use account.toggleUsername, bots.toggleUsername or channels.toggleUsername to mark it as active.
Note that you can't mark as inactive the basic (non-collectible) username, if any.

channels.deactivateAllUsernames may also be used to mark as inactive all collectible usernames associated to a certain supergroup or channel: useful for example when making a group or channel private, by first invoking channels.updateUsername with an empty username to remove the editable username (if present), and then invoking this method to remove all associated collectible usernames.

Use account.reorderUsernames/bots.reorderUsernames/channels.reorderUsernames to change the order of the usernames associated to an account, channel or supergroup: all currently active usernames must be specified.

