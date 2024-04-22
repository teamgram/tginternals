# contacts.Contacts
Info on the current user's contact list.

```
contacts.contactsNotModified#b74ba9d2 = contacts.Contacts;
contacts.contacts#eae87e42 contacts:Vector<Contact> saved_count:int users:Vector<User> = contacts.Contacts;

---functions---

contacts.getContacts#5dd69e12 hash:long = contacts.Contacts;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| contacts.contactsNotModified | Contact list on the server is the same as the list on the client. |
| contacts.contacts | The current user's contact list and info on users. |


## Methods
| Method | Description |
| ---- | ----------- |
| contacts.getContacts | Returns the current user's contact list. |


