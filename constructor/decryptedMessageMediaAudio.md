# decryptedMessageMediaAudio
Audio file attached to a secret chat message.

```
===8===
decryptedMessageMediaAudio#6080758f duration:int size:int key:bytes iv:bytes = DecryptedMessageMedia;

===17===
decryptedMessageMediaAudio#57e0a9cb duration:int mime_type:string size:int key:bytes iv:bytes = DecryptedMessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| duration | int | Audio duration in seconds |
| mime_type | string | MIME-type of the audio fileParameter added in Layer 13. |
| size | int | File size |
| key | bytes | Key to decrypt the attached media file |
| iv | bytes | Initialization vector |


## Type
DecryptedMessageMedia

## Related pages
