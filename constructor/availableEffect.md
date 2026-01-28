# availableEffect
Represents a message effect ».

```
availableEffect#93c3e27e flags:# premium_required:flags.2?true id:long emoticon:string static_icon_id:flags.0?long effect_sticker_id:long effect_animation_id:flags.1?long = AvailableEffect;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| premium_required | flags.2?true | Whether a Premium subscription is required to use this effect. |
| id | long | Unique effect ID. |
| emoticon | string | Emoji corresponding to the effect, to be used as icon for the effect if static_icon_id is not set. |
| static_icon_id | flags.0?long | ID of the document containing the static icon (WEBP) of the effect. |
| effect_sticker_id | long | Contains the preview animation (TGS format »), used for the effect selection menu. |
| effect_animation_id | flags.1?long | If set, contains the actual animated effect (TGS format »). If not set, the animated effect must be set equal to the premium animated sticker effect associated to the animated sticker specified in effect_sticker_id (always different from the preview animation, fetched thanks to the videoSize of type f as specified here »). |


## Type


## Related pages
