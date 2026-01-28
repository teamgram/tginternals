# Telegram Stickers

All users can create, send and share custom artwork using Telegram's open platform for stickers and emoji. The built-in Sticker Editor lets everyday users seamlessly create stickers in the Telegram app with their own photos to share in chats.

Artists and content creators can make vector animations, video files and static images in their preferred apps – then upload them with the @Stickers mini app to share their artwork with over 1 billion users.

To start building your own custom sets, click below:

- Creating Stickers in Telegram

- In-App Sticker Maker

- @Stickers Mini App

- Creating Stickers with Software

- Animated

- Video

- Static

- Custom Emoji

- Importing Stickers from Other Apps

- For Developers

- For Users

### Creating Stickers in Telegram

Any Telegram user can create custom stickers in any Telegram chat – transforming photos into creative artwork that can be saved and shared everywhere.

#### In-App Sticker Maker

You can quickly turn any photo on your device into a custom sticker with added text, drawings, emoji and more using the built-in Sticker Editor. This allows anyone to easily make their own stickers without special software – right in the chat.

The sticker editor also allows you to create packs of custom stickers to share with friends and family.

> To access the Sticker Editor, open the sticker panel from your input field in any chat and tap the (+) button.

#### @Stickers Mini App

The @Stickers allows anyone to create and manage packs of both stickers and emoji, access detailed usage statistics and more – all from one intuitive interface.

> The functions of the @Stickers bot can also be accessed via text commands.

---

### Creating Stickers with Software

Artists and content creators can make stickers in multiple formats using their preferred editing apps – and upload the final animation, video or image files as both stickers and emoji.

#### Animated Stickers and Emoji

Telegram stickers and emoji can move with smooth 60 FPS animations to bring your characters to life in high resolution.

> Animations require Telegram's unique .TGS format – click here for Video Stickers and Emoji made in .WEBM format.

Creating Animations

To create vector-animated stickers and emoji you will need the following:

> The Lottie-based .TGS format allows for incredibly detailed animations that are less than 30 KB in size – six times smaller than the average photo.

Animation Requirements

- The canvas size must be 512х512 pixels.

- Objects must not leave the canvas.

- Animation length must not exceed 3 seconds.

- All animations must be looped.

- Final file size must not exceed 64 KB after rendering in Bodymovin.

- All animations must run at 60 Frames Per Second.

- You must not use the following Adobe After Effects functionality when animating your artwork: Auto-bezier keys, Expressions, Masks, Layer Effects, Images, Solids, Texts, 3D Layers, Merge Paths, Star Shapes, Gradient Strokes, Repeaters, Time Stretching, Time Remapping, Auto-Oriented Layers.

---

#### Video Stickers and Emoji

Stickers and emoji can also be built with .WEBM – an open-source format that is compatible with many graphics editors to create high-detail images. Requires Telegram 8.5 or higher.

Creating Videos

To create stickers and emoji from video files, you only need editing software that lets you export your project as a .WEBM video file.

Video Requirements

> See this Encoding .WEBM with VP9 Guide for details

- For stickers, one side must be exactly 512 pixels in size – the other side can be 512 pixels or less.

- For emoji, the video must be exactly 100x100 pixels in size

- Video duration must not exceed 3 seconds.

- Frame rate can be up to 30 FPS.

- Video should be looped for optimal user experience.

- Video size should not exceed 256 KB.

- Video must be in .WEBM format encoded with the VP9 codec.

- Video must have no audio stream.

---

#### Static Stickers and Emoji

Turn your favorite drawings and memes into packs of images that are easily to share and access on any device.

Creating ImagesTo create static stickers and emoji for Telegram, you only need an image editor that lets you export in .PNG or .WEBP format.

Image Requirements

- For stickers, one side must be exactly 512 pixels in size – the other side can be 512 pixels or less.

- For emoji, images must be exactly 100x100 pixels in size.

- The image file must be in either .PNG or .WEBP format.

> Tip: a transparent background, white stroke and black shadow effect will make your sticker stand out.

#### Custom Emoji

As of version 8.9 released in August 2022, Telegram apps support custom emoji.Emoji use the same technology as stickers, making it very easy to convert your art to both formats. Check out the video and image sections for details on the different size requirements.

> Everyone can create new custom emoji, however, adding and using custom sets is currently an exclusive feature of Telegram Premium users.

#### Adaptive Emoji

If you intend to create a set of simple icons with solid colors that change their color based on where they are used, you can send the command /adaptive when creating your emoji set.

When used as emoji statuses and topic icons, such emoji will match the accent color of the user's theme. When in a message, they will match the text color in that message.

---

### Importing Stickers From Other Apps

Developers can build apps to automate importing stickers using Telegram’s API. With these tools, users can instantly bring their favorite stickers to Telegram.

#### For Users

Users can find apps that allow them to import stickers or quickly generate their own. They can also easily publish custom stickers with the @Stickers bot using .PNG, .WEBP or .WEBM files for stickers from other apps.

#### For Developers

As of version 7.8, Telegram apps support a simple API for importing stickers. Developers can use this to build apps or add tools to apps that let users instantly transfer stickers to Telegram – or create custom stickers from photos or videos.

> Click here for more information about developing apps for importing stickers.

ot menu to create another pack, edit an existing pack, or see statistics.

#### Editing a Sticker Pack

Once you've created one or more packs, you can add, edit or replace stickers in your existing sets.

- Use /addsticker if you have more artwork you'd like to add to a set. Choose one of your packs from the list – the upload process is exactly the same as before.

- Use /editsticker to change the emoji you assigned to a sticker – select the pack and sticker, or simply send the intended sticker from your panel.

- Use /replacesticker if you want to swap out an older sticker for an updated version.

- Use /ordersticker to change the order of stickers in your pack. Choose the pack and one of the stickers, then choose another sticker to appear before it (to the left) in the panel.

- Use /delsticker to remove a sticker from the pack – you can always use /addsticker to add it again if you change your mind.

- Use /seticon to set an icon for your pack or to change the icon. Static sticker packs without a custom icon will use the first sticker as its icon.

> Edits to your sticker packs may take up to an hour to update for all users.

#### Sticker Stats

There are a number of commands that let you see statistics for your stickers – here's what they all do:

- /packstats shows how many times your pack was used, installed and removed – both recently and overall.

- /stats shows how many times an individual sticker has been sent.

- /top shows the most popular stickers from all your packs.

- /packtop shows your most popular sticker packs and their individual stats.

- /topbypack shows the top stickers from a specific sticker pack.

- /packusagetop shows your most popular packs by recent usage.

> You can filter the results of /top, /packtop, /topbypack and /packusagetop. For example /top 20 would show your top 20 stickers, and /topbypack -5 would show the 5 least popular stickers from a pack.

### Importing Stickers From Other Apps

Developers can build apps to automate importing stickers using Telegram’s API. With these tools, users can instantly bring their favorite stickers to Telegram.

#### For Developers

As of version 7.8, Telegram apps support a simple API for importing stickers. Developers can use this to build apps or add tools to apps that let users instantly transfer stickers to Telegram – or create custom stickers from photos or videos.

> Click here for more information about developing apps for importing stickers.

#### For Users

Users can find apps that allow them to import stickers or quickly generate their own. They can also easily publish custom stickers with the @Stickers bot using .PNG, .WEBP or .WEBM files for stickers from other apps.

