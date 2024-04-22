# Privacy
Telegram allows users to specify granular privacy settings, choosing which users can or can't interact with them in certain ways.
### Privacy rules
Schema:
Privacy rules indicate who can or can't do something and are specified by a PrivacyRule, and its input counterpart InputPrivacyRule.
InputPrivacyRule constructors are passed as input to methods that accept privacy rules, while PrivacyRules are contained in constructors returned by the API.
See the type page » for a full list of privacy rules and their descriptions.
One privacy rule in particular should be mentioned separately, (input)privacyValueAllowCloseFriends: this privacy rule, which can be used only when posting stories, refers exclusively to a list of "close friends", that can be modified using contacts.editCloseFriends, passing the full close friend list as a list of user IDs: note that only users in the contact list (even without a phone number) » can be added to the close friends list.
The current list of close friends can be checking which users in our contact list have the close_friend flag set in the associated user constructor, see here » for more info on how to fetch the contact list.
### Privacy keys
Schema:
Privacy keys together with privacy rules » indicate what can or can't someone do and are specified by a PrivacyKey constructor, and its input counterpart InputPrivacyKey.
InputPrivacyKey constructors are passed as input to methods that accept privacy keys, while PrivacyKeys are contained in constructors returned by the API.
See the type page » for a full list of privacy keys and their descriptions.
Use account.getPrivacy to obtain the current set of rules associated to a key, and account.setPrivacy to change it.
Changing the privacy settings will trigger an updatePrivacy, sent to all currently logged in sessions of the current account.
### Global privacy settings
Some global privacy settings can also be fetched and modified using account.getGlobalPrivacySettings and account.setGlobalPrivacySettings.
Global privacy settings are represented by the globalPrivacySettings constructor, that contains the following parameters:
- archive_and_mute_new_noncontact_peers - Whether to archive and mute new chats from non-contacts.
- keep_archived_unmuted - Whether unmuted chats will be kept in the Archive chat list when they get a new message.
- keep_archived_folders - Whether unmuted chats that are always included or pinned in a folder, will be kept in the Archive chat list when they get a new message. Ignored if keep_archived_unmuted is set.
