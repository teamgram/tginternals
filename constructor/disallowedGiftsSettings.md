# disallowedGiftsSettings
Disallow the reception of specific gift types.

```
disallowedGiftsSettings#71f276c4 flags:# disallow_unlimited_stargifts:flags.0?true disallow_limited_stargifts:flags.1?true disallow_unique_stargifts:flags.2?true disallow_premium_gifts:flags.3?true = DisallowedGiftsSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| disallow_unlimited_stargifts | flags.0?true | Disallow the reception of gifts with an unlimited supply (those with the starGift.limited flag not set). |
| disallow_limited_stargifts | flags.1?true | Disallow the reception of limited-supply gifts (those with the starGift.limited flag set). |
| disallow_unique_stargifts | flags.2?true | Disallow the reception of collectible gifts ». |
| disallow_premium_gifts | flags.3?true | Disallow the reception of gifted Telegram Premium subscriptions ». |


## Type
DisallowedGiftsSettings

## Related pages
