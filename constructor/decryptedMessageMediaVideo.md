# decryptedMessageMediaVideo
Video attached to an encrypted message.

```
===8===
decryptedMessageMediaVideo#4cee6ef3 thumb:bytes thumb_w:int thumb_h:int duration:int w:int h:int size:int key:bytes iv:bytes = DecryptedMessageMedia;

===17===
decryptedMessageMediaVideo#524a415d thumb:bytes thumb_w:int thumb_h:int duration:int mime_type:string w:int h:int size:int key:bytes iv:bytes = DecryptedMessageMedia;

===45===
decryptedMessageMediaVideo#970c8c0e thumb:bytes thumb_w:int thumb_h:int duration:int mime_type:string w:int h:int size:int key:bytes iv:bytes caption:string = DecryptedMessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| thumb | bytes | Content of thumbnail file (JPEG file, quality 55, set in a square 90x90) |
| thumb_w | int | Thumbnail width |
| thumb_h | int | Thumbnail height |
| duration | int | Duration of video in seconds |
| mime_type | string | MIME-type of the video fileParameter added in Layer 17. |
| w | int | Image width |
| h | int | Image height |
| size | int | File size |
| key | bytes | Key to decrypt the attached video file |
| iv | bytes | Initialization vector |
| caption | string | Caption |


## Type
DecryptedMessageMedia

## Related pages
