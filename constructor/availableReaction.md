# availableReaction
Animations associated with a message reaction

```
availableReaction#c077ec01 flags:# inactive:flags.0?true premium:flags.2?true reaction:string title:string static_icon:Document appear_animation:Document select_animation:Document activate_animation:Document effect_animation:Document around_animation:flags.1?Document center_icon:flags.1?Document = AvailableReaction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inactive | flags.0?true | If not set, the reaction can be added to new messages and enabled in chats. |
| premium | flags.2?true | Whether this reaction can only be used by Telegram Premium users |
| reaction | string | Reaction emoji |
| title | string | Reaction description |
| static_icon | Document | Static icon for the reaction |
| appear_animation | Document | The animated sticker to show when the user opens the reaction dropdown |
| select_animation | Document | The animated sticker to show when the user hovers over the reaction |
| activate_animation | Document | The animated sticker to show when the reaction is chosen and activated |
| effect_animation | Document | The background effect (still an animated sticker) to play under the activate_animation, when the reaction is chosen and activated |
| around_animation | flags.1?Document | The animation that plays around the button when you press an existing reaction (played together with center_icon). |
| center_icon | flags.1?Document | The animation of the emoji inside the button when you press an existing reaction (played together with around_animation). |


## Type
AvailableReaction

## Related pages
