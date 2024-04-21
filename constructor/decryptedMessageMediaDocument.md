# decryptedMessageMediaDocument
Document attached to a message in a secret chat.

```
===8===
decryptedMessageMediaDocument#b095434b thumb:bytes thumb_w:int thumb_h:int file_name:string mime_type:string size:int key:bytes iv:bytes = DecryptedMessageMedia;

===45===
decryptedMessageMediaDocument#7afe8ae2 thumb:bytes thumb_w:int thumb_h:int mime_type:string size:int key:bytes iv:bytes attributes:Vector<DocumentAttribute> caption:string = DecryptedMessageMedia;

===143===
decryptedMessageMediaDocument#6abd9782 thumb:bytes thumb_w:int thumb_h:int mime_type:string size:long key:bytes iv:bytes attributes:Vector<DocumentAttribute> caption:string = DecryptedMessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| thumb | bytes | Thumbnail-file contents (JPEG-file, quality 55, set in a 90x90 square) |
| thumb_w | int | Thumbnail width |
| thumb_h | int | Thumbnail height |
| mime_type | string | File MIME-type |
| size | long | Document size (int on layer <143, long on layer >=143) |
| key | bytes | Key to decrypt the attached document file |
| iv | bytes | Initialization |
| attributes | Vector<DocumentAttribute> | Document attributes for media types |
| caption | string | Caption |


## Type
DecryptedMessageMedia

## Related pages
