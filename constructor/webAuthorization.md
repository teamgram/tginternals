# webAuthorization
Represents a bot logged in using the Telegram login widget

```
webAuthorization#a6f8f452 hash:long bot_id:long domain:string browser:string platform:string date_created:int date_active:int ip:string region:string = WebAuthorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| hash | long | Authorization hash |
| bot_id | long | Bot ID |
| domain | string | The domain name of the website on which the user has logged in. |
| browser | string | Browser user-agent |
| platform | string | Platform |
| date_created | int | When was the web session created |
| date_active | int | When was the web session last active |
| ip | string | IP address |
| region | string | Region, determined from IP address |


## Type
WebAuthorization

## Related pages
