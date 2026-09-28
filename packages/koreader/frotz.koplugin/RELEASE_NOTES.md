# 3.0

This release adds support for **Twine** games. This is the most popular category of interactive fiction for the last 10 years: as these are more choice-based games, they are easier to create and to play. Basically they don't need any typing.

This adds over **1000 new games** to the supported game list!

### Adding Twine support

This was a huge project, as Koreader misses a modern web browser, so a custom engine based on *QuickJS* javascript library needed to be created. As some Twine games use custom javascript stuff, some games won't work. Check out the [**games compatibility list**](https://github.com/kbarni/frotz.koplugin/blob/main/twinegames.md) before playing a game.

Normally *twine* games are stylized (as they are HTML files), but this plugin keeps the text-only mode. This also helps the games to adapt to the small e-ink screens.

Most twine games can be downloaded from [IFDB](https://ifdb.org/search?searchfor=tag:twine) as zip files, but others are only available on itch.io (or similar platforms). As this plugin only needs the base HTML file, so you can open the game in a browser, then save the HTML file and transfer it to your reader device.

### Support for SimpleUI and ZenUI

Frots integrates now with these custom launchers: you can add *Frotz* as a homescreen widget (with the list of the last played games) or as a quick action.

Also check out the new [**Beginner's tutorial for IF games**](https://github.com/kbarni/frotz.koplugin/blob/main/TUTORIAL.md)

# 2.3

Frotz 2.3 adds a game browser and downloader using IFDB database.

- *Lists:* Top rated, Most rated, Newest releases, Short games, Surprise me — limited to Z-machine and/or Glulx games (tap Formats to choose)
- *Search…* by title or author, or with IFDB filters such as tag:horror, author:"Emily Short", rating:4-, playtime:-1h
- *Tap a game* for its description, rating, play time and tags, its cover, and Download. Zip files are unpacked automatically; the game is saved to the download folder (default koreader/ifgames/<game title>/) and can be started right away

# 2.2

**Frotz now has basic image support.**

Images will appear as link texts like `[Illustration 1]` in the transcription. Click the link to display the image.

It only supports story related images, not decorative images (like text separators or border decorations).

You can test it with Everybody dies (several images) or Violet or Lost pig (cover image)

# 2.1

This release fixes the use of Bluetooth keyboard with Frotz.

# 2.0

Major rewrite of the plugin. The engine was changed from **Frotz** to **Git** and **Bocfel**, based on RemGlk backend.

This allows support for both **Z-machine** and **Glulx** formats, which covers almost every modern IF game.
This also allows to display the **status header bar** and  **better text formatting** (bold/italic)
A new default font was also added, giving a *typewriter* style and native bold/italic styles.:

The correct binary is now selected automatically, don't need to copy it manually to the bin folder. Added support for **aarch64** architecture, covering more advanced e-ink tablets like the Remarkable.

Solves issues #3 #4 #6

Before installing, remove the old files from Frotz 1.0
