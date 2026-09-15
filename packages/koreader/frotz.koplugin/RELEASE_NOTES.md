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

# 1.1

Now with dictionary lookup support
<img width="392" height="498" alt="Screenshot frotz dict sm" src="https://github.com/user-attachments/assets/957d84e6-4ffd-47f1-802c-4a9794ee9ce8" />
