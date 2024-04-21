# inputSingleMedia
A single media in an album or grouped media sent with messages.sendMultiMedia.

```
inputSingleMedia#1cc6e91f flags:# media:InputMedia random_id:long message:string entities:flags.0?Vector<MessageEntity> = InputSingleMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| media | InputMedia | The media |
| random_id | long | Unique client media ID required to prevent message resending |
| message | string | A caption for the media |
| entities | flags.0?Vector<MessageEntity> | Message entities for styled text |


## Type
InputSingleMedia

## Related pages
