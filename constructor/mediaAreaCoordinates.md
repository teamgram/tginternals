# mediaAreaCoordinates
Coordinates and size of a clickable rectangular area on top of a story.

```
mediaAreaCoordinates#cfc9e002 flags:# x:double y:double w:double h:double rotation:double radius:flags.0?double = MediaAreaCoordinates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| x | double | The abscissa of the rectangle's center, as a percentage of the media width (0-100). |
| y | double | The ordinate of the rectangle's center, as a percentage of the media height (0-100). |
| w | double | The width of the rectangle, as a percentage of the media width (0-100). |
| h | double | The height of the rectangle, as a percentage of the media height (0-100). |
| rotation | double | Clockwise rotation angle of the rectangle, in degrees (0-360). |
| radius | flags.0?double | The radius of the rectangle corner rounding, as a percentage of the media width. |


## Type
MediaAreaCoordinates

## Related pages
