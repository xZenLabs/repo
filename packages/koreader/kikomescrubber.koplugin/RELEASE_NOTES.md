# v2.0.0 · 2026-11-03

## What's new
This update turns Book Details into a place to actually work with your books. Browse every bookmark, highlight and note in one list. Edit a book's metadata, rating, status, collections and file from a single screen. And in Files, move books into any folder with the new **+**.

### Book Details: Annotations
A new bookmark button beside **Read now** opens every annotation in the book.
- Bookmarks, highlights and notes in one list.
- Filter by type, and by highlight style (highlight, underline, invert, strikethrough).
- Tap an annotation to read it in full, with its date, chapter, quote and note.
- **Show in book** jumps to its page.

### Book Details: Edit
The pencil button now opens a full editing screen for the book.
- **Favorite, review and rating:** heart, a short review and five stars.
- **Status:** Reading, On hold or Finished.
- **Metadata:** edit title, authors, series, series number, language, keywords and description.
  - You can choose to write the changes into the EPUB itself, with an optional backup copy.
  - Restore the original metadata at any time.
- **Collections:** add the book to any of your collections.
- **Book settings:**
  - Reset this document.
  - Export its notes as a .md file.
  - Refresh metadata.
  - Buttons from your other plugins.
- **File:** Rename, Copy, Cut and Delete the book's file.

### Library > Files: Move to folder
A new **+** button moves books into the folder you have open.
- Pick from a list of your books; each one shows the folder it is in now.
- The ticked books move into the open folder.

### Also
- Holding a book in Home, or in Library tabs other than Files and Collections, opens its details directly.
- In Files and Collections, **KOReader menu** is now **Edit book**, and opens the Edit screen.
- Holding a folder or collection in Home shows the same menu as in Library.

## Installation
1. Download `KiKomeScrubber.koplugin.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `KiKomeScrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, use **Check for updates** in KiKome's Settings, or replace the folder. To uninstall, delete it.

# v1.1.0 · 2026-11-01

# KiKome 1.1.0

KiKome 1.1.0 brings a Library with easier-to-manage folders and collections, allowing you to create them directly from books, as well as add or remove multiple books in batches. The Home screen now features filters by status, alphabetical order, and language, supporting up to 12 chips (including collections and a new genres chip) alongside a customizable Genres tab that you can reorder or disable. Additionally, the plugin is faster on startup, when opening Home from a book, and when loading covers, introducing a new keyboard, reduced screen flashing, and improved landscape support.

## New in Library

**New menus**
- **New Folder:** move any books you want into a new folder and give it a name. Each book shows its path, so you always know where it's coming from. Find it in Library › Files › More.
- **New Collection:** pick the books you want and name your new collection.
- **Add to Collection:** select books to add to a specific collection.
- All three menus include the plugin's sort, filters and search.

**Collections and folders**
- Select several books inside a collection, by holding a book or from More, and remove them all at once.
- Hold a collection or folder to open its menu:
  - Collection: Rename, Remove
  - Folder: Rename, Set as home, Delete

**Tabs**
- New **Genres** tab.
- New **Library › Tabs** option: reorder every tab however you like, or turn them off.
- **To be read** and **Favorites** can now be turned off in Collections, just like the Collections chip on Home.

**More menu**
- Tapping More on Home and on some tabs now opens a menu with **Refresh Library**. Handy after adding a book.

## New on Home

**Filters**
- **Status:** Read, Unread, On hold, Reading
- **Alphabetical:** A–Z, Z–A #1 
- **By language**

**Shelves chips**
- The limit goes up to **12 chips**.
- Collections can now be chips.
- New **Genres** chip, off by default.

## Design

- **New messages and popups.** Simpler and more consistent with the plugin, used everywhere in KiKome, including a new confirmation popup (for example, when deleting a folder).
- **New keyboard.** It doesn't replace KOReader's; KiKome simply uses it whenever you need to type.
- **New book state: On hold.** It now shows in cover badges, Book Details and Info.
- **Status bar and its popups.** Redesigned to match the rest of the plugin.

## Performance

The whole plugin has been optimized.
- KiKome loads much faster, both when KOReader starts and when you open its screens.
- Leaving a book and getting back to Home is much quicker. The book stays parked in the background and closes later, while you're not using the device.
- Reopening a book you just left is almost immediate.
- Covers are cached, in memory and on disk, so they don't have to be decoded and scaled again each time.
- Your library's information is read in a single pass and saved, so after a restart it loads without searching every book again.
- Screens hidden behind KiKome no longer refresh the display for no reason.
- Menus that sometimes stayed blank until you touched a button now appear right away.
- The keyboard only refreshes the key you press and the text field, instead of the whole screen, so there's much less ghosting.

## Fixes

- In grid view, the number of books and folders per row is now calculated automatically instead of always being fixed. The spacing between covers has also been tightened.
- Optimized for landscape mode.
- Improved scroll bar: hold it and drag up or down.
- Technical improvements to copy, cut and delete.

## Installation
1. Download `KiKomeScrubber.koplugin.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `KiKomeScrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, use **Check for updates** in KiKome's Settings, or replace the folder. To uninstall, delete it.

# v1.0.0 · 2026-10-28

## KiKome 1.0

Hello, KiKome. A calm, rounded home for your library in KOReader.

Based on [Kobold](https://github.com/unitreign/kobold), with a lot of new ideas on top.

### Home
- Your recent books up front. Swipe through them and pick up where you left off.
- Shelves you make your own. Add chips for Collections, To be read, Favorites, or any folder.
- Grid or list, with or without shelf boards.

### Library
- Browse by Books, Authors, Series, Collections, or Files.
- Filter, sort, and group in a tap.
- In Files, select books and copy, move, or delete them. Progress, history, and covers come along.
- Paste into any folder, and make a New Folder anywhere.

### Book details
- A clean page for every book: progress, synopsis, keywords, and file info.
- Tap the cover to see it full screen.

### Little touches
- A soft "Opening" pill appears on a book's cover while it loads, and a small "Closing" pill when you leave it.
- Rounded corners and cover outlines, if you like them.
- Quick panels for brightness, Wi-Fi, battery, and the clock.
- Load every missing cover in one go.
- Check for updates right from Settings.

### Thank you
To [Kobold](https://github.com/unitreign/kobold) and [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin). KiKome wouldn't exist without them.

## Installation
1. Download `KiKomeScrubber.koplugin.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `KiKomeScrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, use **Check for updates** in KiKome's Settings, or replace the folder. To uninstall, delete it.
