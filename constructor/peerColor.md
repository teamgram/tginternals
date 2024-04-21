# peerColor
Represents a color palette ».

```
peerColor#b54b5acf flags:# color:flags.0?int background_emoji_id:flags.1?long = PeerColor;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| color | flags.0?int | Color palette ID, see here » for more info; if not set, the default palette should be used. |
| background_emoji_id | flags.1?long | Optional custom emoji ID used to generate the pattern. |


## Type
PeerColor

## Related pages
