# contacts.ContactBirthdays
Birthday information of our contacts.

```
contacts.contactBirthdays#114ff30d contacts:Vector<ContactBirthday> users:Vector<User> = contacts.ContactBirthdays;

---functions---

contacts.getBirthdays#daeda864 = contacts.ContactBirthdays;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| contacts.contactBirthdays | Birthday information of our contacts. |


## Methods
| Method | Description |
| ---- | ----------- |
| contacts.getBirthdays | Fetch all users with birthdays that fall within +1/-1 days, relative to the current day: this method should be invoked by clients every 6-8 hours, and if the result is non-empty, it should be used to appropriately update locally cached birthday information in user.birthday.See here » for more info. |


