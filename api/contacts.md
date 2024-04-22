# Contacts

Working with contacts.

### Importing phone contacts

Schema:

To upload the local contact list to Telegram and see which contacts are already signed up on telegram, use contacts.importContacts, passing an array of inputPhoneContact constructors, containing:

- phone - The phone number in international format

- first_name - First name

- last_name - Last name, can be empty

- client_id - An arbitrary 64-bit integer (not the contact's Telegram user ID, since we do not have it yet); make sure there are no collisions between the client_ids passed to a single contacts.importContacts call (for example, use a simple incremental ID starting from 0)

The method will return a contacts.importedContacts constructor, containing the following fields:

- imported - A list of successfully imported contacts that have an associated Telegram account as importedContact constructors.

- user_id is the Telegram user ID, client_id is the client_id associated to the contact, passed during the method call.

- Note that according to the user's privacy settings, not all contacts which have an associated Telegram account may be returned here.

- users - Contains info about the Telegram users mentioned in imported

- popular_invites - Contains info about popular contacts: each popularContact constructor indicates that the contact with the specified client_id was imported imported times by that many Telegram users.

- retry_contacts - List of contact ids that could not be imported due to a server-side system limitation and have to be reimported with another call to contacts.importedContacts.

### Adding Telegram users as contacts

Schema:

Telegram users may also be added to the contact list (even if we do not have access to their phone number!) using contacts.addContact.

Set the add_phone_privacy_exception flag if we wish to allow the other user to see our phone number: this flag must be set if the need_contacts_exception flag of peerSettings is set (see the action bar documentation for more info »).

The other user will be offered to also add us to the contact list via the add contact action bar: if they accept, their phone number will be automatically added to our contact.

### Share our phone number

This method is invoked if the user clicks on the add contact button in the add contact chat bar.

The bar is activated only if the other user has added us as a contact using contacts.addContact without using a phone number, and none of the add_contact, report_spam, block_contact bar flags are set, the share_contact flag are be set, indicating we can invoke contacts.acceptContact to share our phone number with the other user.

### Fetching the contact list

Schema:

Use contacts.getContacts to obtain all members of the contact list that have an associated Telegram account.

Use contacts.getContactIDs to obtain an array of Telegram user IDs for all contacts (0 is returned for contacts do not have an associated Telegram account or have hidden their account using privacy settings).

To obtain the full contact list, including contacts which do not have an associated Telegram account, use contacts.getSaved in combination with a takeout session ».

### Getting contact statuses

Schema:

Use contacts.getStatuses to obtain the online statuses of all contacts with an accessible Telegram account.

### Searching for contacts

Schema:

Use contacts.search to search within the contact list.

### Deleting contacts

Schema:

Use contacts.deleteContacts to delete contacts with an associated Telegram account; the returned Updates will contain updated user information.

Use contacts.deleteByPhones to delete contacts by their phone number, even if they don't have an associated Telegram account.

Use contacts.resetSaved to remove all contacts without an associated Telegram account.

