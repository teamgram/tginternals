# decryptedMessageMediaPhoto
Photo attached to an encrypted message.

```
===8===
decryptedMessageMediaPhoto#32798a8c thumb:bytes thumb_w:int thumb_h:int w:int h:int size:int key:bytes iv:bytes = DecryptedMessageMedia;

===45===
decryptedMessageMediaPhoto#f1fa8d78 thumb:bytes thumb_w:int thumb_h:int w:int h:int size:int key:bytes iv:bytes caption:string = DecryptedMessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| thumb | bytes | Content of thumbnail file (JPEGfile, quality 55, set in a square 90x90) |
| thumb_w | int | Thumbnail width |
| thumb_h | int | Thumbnail height |
| w | int | Photo width |
| h | int | Photo height |
| size | int | Size of the photo in bytes |
| key | bytes | Key to decrypt an attached file with a full version |
| iv | bytes | Initialization vector |
| caption | string | Caption |


## Type
DecryptedMessageMedia

## Related pages
