# Action bar

Sometimes, when interacting with Telegram users via private or secret chats, an action bar must be shown on top of the chat, offering convenient action buttons or notices regarding the user.

Schema:

The action bar is represented by the peerSettings constructor, fetchable using messages.getPeerSettings; it is also contained in the userFull constructor returned by users.getFullUser.

Changes to the chat bar may also be notified by the server using updatePeerSettings.

The currently active action bar may also be dismissed using messages.hidePeerSettingsBar.

What follows is a list of the various (mutually exclusive) chat bar types, along with the condition used to identify each type, by checking the appropriate flags of peerSettings.

### Report spam, block or add contact

This action bar, associated to a private or secret chat, offers the user buttons to:

- Report the chat for spam using account.reportPeer and inputReportReasonSpam.

- If the other user has an emoji status, then the bar should also show a notice, indicating that the emoji status is shown next to the user's name because they have purchased Telegram Premium (i.e. this is useful to avoid issues if the user uses an emoji status similar to a verified checkmark).

- Additionally, if the chat was automatically archived » (according to peerSettings.autoarchived), an extra button can be shown to unarchive the chat as specified here » instead of reporting it.

- Add the other user of the chat to the contact list using contacts.addContact.

- Optionally, the peerSettings.need_contacts_exception flag may also be set: if so, the add_phone_privacy_exception flag must be set if the user clicks on the add contact button, invoking contacts.addContact.

- Block the other user of the chat from writing to us using contacts.block (without setting the my_stories_from flag).

Condition: the peerSettings.report_spam, peerSettings.add_contact, peerSettings.block_contact flags must all be set.

Additionally, if the peerSettings.geo_distance flag is set, the bar should also display the distance between us and the user, indicating that the user found us by invoking contacts.getLocated, because we are currently advertising our location with the same method.

### Report spam or unarchive

This action bar, associated to a private or secret chat, offers the user a button to report the chat for spam using account.reportPeer and inputReportReasonSpam.

If the other user has an emoji status, then the bar should also show a notice, indicating that the emoji status is shown next to the user's name because they have purchased Telegram Premium (i.e. this is useful to avoid issues if the user uses an emoji status similar to a verified checkmark).

Condition: the peerSettings.report_spam flag must be set, and the peerSettings.add_contact, peerSettings.block_contact flags must not be set.

Additionally, if the chat was automatically archived » (according to peerSettings.autoarchived), an extra button can be shown to unarchive the chat as specified here » instead of reporting it.

### Add contact

This action bar, associated to a private or secret chat, offers the user a button to add the other user of the chat to the contact list using contacts.addContact.

Conditions: the peerSettings.add_contact flag must be set and:

- For secret chats, the chat must not be archived.

- For private chats, the block_contact and report_spam flags must not be set.

Optionally, the peerSettings.need_contacts_exception flag may also be set: if so, the add_phone_privacy_exception flag must be set if the user clicks on the add contact button, invoking contacts.addContact.

### Share phone number

This action bar, associated to a private or secret chat, offers the user a button to share their phone number with the other user using contacts.acceptContact.

Condition: the peerSettings.share_contact flag must be set.

This flag is set and the bar is activated only if the other user has added us as a contact using contacts.addContact, without using a phone number, and none of the add_contact, report_spam, block_contact flags are set.

### Report irrelevant geolocation

This bar indicates that the associated location-based supergroup can be reported for having an unrelated location using a bar button that invokes account.reportPeer with reason inputReportReasonGeoIrrelevant.

Condition: the peerSettings.report_geo flag must be set.

### Invite new members

This bar indicates that the associated group was created recently, and it offers a bar button to invite new members using messages.addChatUser or channels.inviteToChannel, depending on whether the associated peer is a group or a supergroup.

Condition: the peerSettings.invite_members flag must be set.

### An admin from a recent join request is contacting you

This bar indicates that the associated private or secret chat is a chat with an administrator of a group or channel to which the user sent a join request, see here for more info on join requests ».

Condition: the request_chat_title and request_chat_date fields of peerSettings must both be set; optionally request_chat_broadcast may also be set:

- request_chat_title - Contains the group/channel's title.

- request_chat_date - Contains the timestamp indicating when the join request was sent.

- request_chat_broadcast - This flag is set if the join request is related to a channel (otherwise, the join request is related to a group).

