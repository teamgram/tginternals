# urlAuthResultRequest
Details about the authorization request, for more info click here »

```
urlAuthResultRequest#92d33a0e flags:# request_write_access:flags.0?true bot:User domain:string = UrlAuthResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| request_write_access | flags.0?true | Whether the bot would like to send messages to the user |
| bot | User | Username of a bot, which will be used for user authorization. If not specified, the current bot's username will be assumed. The url's domain must be the same as the domain linked with the bot. See Linking your domain to the bot for more details. |
| domain | string | The domain name of the website on which the user will log in. |


## Type
UrlAuthResult

## Related pages
