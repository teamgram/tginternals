# StoryAlbum
Represents a story album ».

```
storyAlbum#9325705a flags:# album_id:int title:string icon_photo:flags.0?Photo icon_video:flags.1?Document = StoryAlbum;

---functions---

stories.createAlbum#a36396e5 peer:InputPeer title:string stories:Vector<int> = StoryAlbum;
stories.updateAlbum#5e5259b6 flags:# peer:InputPeer album_id:int title:flags.0?string delete_stories:flags.1?Vector<int> add_stories:flags.2?Vector<int> order:flags.3?Vector<int> = StoryAlbum;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| storyAlbum | Represents a story album ». |


## Methods
| Method | Description |
| ---- | ----------- |
| stories.createAlbum | Creates a story album. |
| stories.updateAlbum | Rename a story albums », or add, delete or reorder stories in it. |


