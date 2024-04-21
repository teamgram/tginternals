# RestrictionReason
Restriction reason

```
restrictionReason#d072acb4 platform:string reason:string text:string = RestrictionReason;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| restrictionReason | Restriction reason.Contains the reason why access to a certain object must be restricted. Clients are supposed to deny access to the channel if the platform field is equal to all or to the current platform (ios, android, wp, etc.). Platforms can be concatenated (ios-android, ios-wp), unknown platforms are to be ignored. The text is the error message that should be shown to the user. |


## Methods
| Method | Description |
| ---- | ----------- |


