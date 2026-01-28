# contacts.getContacts
Returns the current user's contact list.

```
contacts.contactsNotModified#b74ba9d2 = contacts.Contacts;
contacts.contacts#eae87e42 contacts:Vector<Contact> saved_count:int users:Vector<User> = contacts.Contacts;
---functions---
contacts.getContacts#5dd69e12 hash:long = contacts.Contacts;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| hash | long | Hash used for caching, for more info click here.Note that the hash is computed using the usual algorithm, passing to the algorithm first the previously returned contacts.contacts.saved_count field, then max 100000 sorted user IDs from the contact list, including the ID of the currently logged in user if it is saved as a contact. Example: tdlib implementation. |


## Result
contacts.Contacts

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

