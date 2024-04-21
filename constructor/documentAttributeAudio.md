# documentAttributeAudio
Represents an audio file

```
documentAttributeAudio#9852f9c6 flags:# voice:flags.10?true duration:int title:flags.0?string performer:flags.1?string waveform:flags.2?bytes = DocumentAttribute;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| voice | flags.10?true | Whether this is a voice message |
| duration | int | Duration in seconds |
| title | flags.0?string | Name of song |
| performer | flags.1?string | Performer |
| waveform | flags.2?bytes | Waveform: consists in a series of bitpacked 5-bit values. Example implementation: android. |


## Type
DocumentAttribute

## Related pages
