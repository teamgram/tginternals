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
| hash | long | If there already is a full contact list on the client, a hash of a the list of contact IDs in ascending order may be passed in this parameter. If the contact set was not changed, (contacts.contactsNotModified) will be returned. |


## Result
contacts.Contacts

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

