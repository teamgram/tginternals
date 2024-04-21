# chatInvite
Chat invite info

```
chatInvite#cde0ec40 flags:# channel:flags.0?true broadcast:flags.1?true public:flags.2?true megagroup:flags.3?true request_needed:flags.6?true verified:flags.7?true scam:flags.8?true fake:flags.9?true title:string about:flags.5?string photo:Photo participants_count:int participants:flags.4?Vector<User> color:int = ChatInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel | flags.0?true | Whether this is a channel/supergroup or a normal group |
| broadcast | flags.1?true | Whether this is a channel |
| public | flags.2?true | Whether this is a public channel/supergroup |
| megagroup | flags.3?true | Whether this is a supergroup |
| request_needed | flags.6?true | Whether the join request » must be first approved by an administrator |
| verified | flags.7?true | Is this chat or channel verified by Telegram? |
| scam | flags.8?true | This chat is probably a scam |
| fake | flags.9?true | If set, this chat was reported by many users as a fake or scam: be careful when interacting with it. |
| title | string | Chat/supergroup/channel title |
| about | flags.5?string | Description of the group of channel |
| photo | Photo | Chat/supergroup/channel photo |
| participants_count | int | Participant count |
| participants | flags.4?Vector<User> | A few of the participants that are in the group |
| color | int | Profile color palette ID |


## Type
ChatInvite

## Related pages
