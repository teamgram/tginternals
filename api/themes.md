# Themes

Telegram apps support generating, sharing and synchronizing app themes.

### Uploading theme files

Theme files can be uploaded using account.uploadTheme: optionally a JPEG thumbnail for the theme can also be provided to thumb.
The resulting document should be used when creating or updating themes.

The actual content of the theme file depends on the formats supported by the theming engine of the client.

### Creating themes

Use account.createTheme to create a theme, see the method page for more info about the parameters ».

The resulting theme can be shared by generating a theme deep link » using either a user-provided slug, or an autogenerated one by leaving the slug parameter empty and using the returned slug.

### Updating themes

A previously uploaded theme can be modified by the creator using account.updateTheme, passing the same parameters used when creating themes, along with an InputTheme containing the ID and access hash parameters from the theme constructor returned by account.createTheme or account.getTheme.

All users that have installed this theme will receive an updateTheme with the updated theme.

### Installing themes

Once you've created your theme or received a theme deep link, it can be installed as follows.

First of all, to get info about a theme from a theme deep link use account.getTheme with inputThemeSlug.

The API keeps a list of theme that the user can apply.
To fetch the list use account.getThemes.
To save a theme to the list use account.saveTheme with unsave=false.
To remove a theme from the list use account.saveTheme with unsave=true.

When a client applies a theme, call account.installTheme to signal the installation to the server.

In all methods, format indicates the theme format, a string that identifies the theming engines supported by the client.

