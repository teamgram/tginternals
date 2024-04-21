# inputPhoneContact
Phone contact.

```
inputPhoneContact#f392b7f4 client_id:long phone:string first_name:string last_name:string = InputContact;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| client_id | long | An arbitrary 64-bit integer: it should be set, for example, to an incremental number when using contacts.importContacts, in order to retry importing only the contacts that weren't imported successfully, according to the client_ids returned in contacts.importedContacts.retry_contacts. |
| phone | string | Phone number |
| first_name | string | Contact's first name |
| last_name | string | Contact's last name |


## Type
InputContact

## Related pages
