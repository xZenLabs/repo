# v2.3.0 · 2026-11-15

## What's new

### Actions (new Home chip)
The biggest addition in this release. **Actions** is a new chip in Home that lets you build your own shortcuts. Each shortcut is a tile with a name and an icon of your choice, and one tap runs it. It is off by default: turn it on under Settings > Shelves.

A tile can run either of two things:
- **A KOReader action.** These are the same actions gestures and profiles can run, including the ones other plugins register (toggle night mode, open the file search, and so on).
- **A plugin.** Any entry a plugin puts in KOReader's main menu, so you can open a plugin's screen straight from Home.
**Creating an action:** tap the "+" tile at the end of the chip, then:
1. Choose whether it runs a KOReader action or a plugin, and pick which one from the list.
2. Give it a name (it starts with the name of what it runs).
3. Choose an icon, or skip it to use the default one. You can use KiKome's own icons or any SVG/PNG file from your device.
**Managing actions:** hold a tile to rename it, change its icon, change what it runs, move it earlier or later, or delete it. Deleting a tile only removes the shortcut; what it ran is not touched.
**Hiding the "+" tile:** once your actions are set, you can hide the "+" tile from the More menu of Home. While it is hidden, an "Add an action" row in the same menu replaces it.
Your actions are stored in KOReader's settings, so they survive plugin updates.

### Home
- **Current book view:** Home can now show a single "Current book" card instead of the recent books row. It shows the cover, title, author, reading progress and quick action buttons, which take a pale tint from the book's cover color.
- **Literary clock (only English):** A third option under Settings > Home > Top of Home. It shows a quote from a book mentioning the current time—with the time phrase highlighted—along with the book's title and author on a soft grey card that updates every minute. Below the card sit quick action buttons to open your current book, its annotations, or its edit screen, tinted from the book's cover color. 

- **Hold menu on folders and collections:** Long-pressing a folder or a collection in Home now opens the same options menu you get in Library (open, rename, add, remove and more). Before, this only worked in Library.
- **Selection mode on Home:** Everything about selection mode now works in Home too: Select from the hold menu or from More, the Selection menu (Copy, Move, Select all, Delete), Add to collection, and Move to folder.

### Collections
- **New "Uncollected" collection:** An automatic list of every book that isn't in any collection. A book leaves it by itself as soon as you add it to one, so it works as an inbox of books still to organize. It has options of its own:
  - **Add to collections:** hold a book and add it to one or several collections right away, without going through Select.
  - **Select:** pick several books and add them all to collections in one step, with "Select all" available.
  - **Disable collection:** hold the collection itself to turn it off. A short guide tells you how to bring it back.
- **Optional:** It can be switched on or off at any time under Settings > Shelves > Collections (Home) or Settings > Library options > Tabs > Collections (Library), in "Show in Collections".

### Annotations
- **Colored highlights:** Quotes in the Annotations list now sit on a soft pill in the same hue as the highlight, in a lighter shade.
- **Color names:** The line with the chapter and page now also names the color (e.g. `Chapter 3 · Page 45 · Yellow`). This helps on e-ink screens that can't show color. It applies to highlights, underlines and strikethroughs.

### Settings
- **Font choice:** You can now choose between the primary and the secondary font.

### Fixes
- **More room for shelves on smaller screens:** Tightened the vertical spacing at the top of Home so the shelves below get more room on smaller e-readers.
- **Back gesture:** Back now steps back one level (closing menus, leaving selection mode) instead of dropping you out of the plugin.
- **Exit confirmation:** KiKome now asks for confirmation before you leave it.
- Technical improvements on the stable pages options.

## Installation
1. Download `KiKomeScrubber.koplugin.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `KiKomeScrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, use **Check for updates** in KiKome's Settings, or replace the folder. To uninstall, delete it.

# v2.2.0 · 2026-11-09

## What's new

### Metadata
- **Cover.** In *Edit > Metadata*, the Cover row opens a screen with three ways to change a book's cover:
  - **Search online**: Apple Books, Open Library, Amazon and Google Books.
  - **Search with other words**: for example a title in another language, or another author.
  - **Choose from this device**: a JPG or PNG you already have.

  Once a custom cover is set, a fourth option appears: **Use the book's own cover** removes it.
- **More details.** A new page with **Publisher**, **Publication year**, **ISBN** and **Pages**.
- **Search online.** Most fields (title, authors, series, language, keywords, description, publisher, year, ISBN, pages) have a *Search online* row. It lists what online sources say about the book and you pick a value. Nothing changes until you choose.

### Stable pages
Page numbers that stay the same whatever the font size, like in a printed book.

1. **Optional:** set the book's page count in *Edit > Metadata > More details > Pages*.
2. **Choose how books are numbered** in *Settings > General > Books > Stable pages*:
   - **Off**: no stable pages.
   - **KOReader numbering**: KOReader's own count.
   - **Metadata page count**: uses *Pages* when the book has it, and KOReader's numbering when it doesn't.
3. **Change it for one book** in *Edit > Book settings > Stable pages*, with the same three options.

With no choice made, KiKome follows KOReader's own setting. Turning stable pages on for all books asks for confirmation first, because books you are already reading may show a different page number and total. Books update when you open them.

### KiKome in the reader menu
- Inside a book, a single **KiKome** row now sits in the **Tools** tab, with *Open KiKome Home* and *Configurations* inside it.

### Fixes
- **Start with > KiKome** now opens KiKome directly, which avoids glitches at startup.

## Installation
1. Download `KiKomeScrubber.koplugin.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `KiKomeScrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, use **Check for updates** in KiKome's Settings, or replace the folder. To uninstall, delete it.

# v2.1.0 · 2026-11-06

## v2.1

### New
- **Select button** in edit mode.
- **Customizable clock**: pick a preset layout (time, weekday + time, time + date, two lines...) or write your own custom pattern, e.g. `%K, %a %e %b` shows `22:42, Thu 5 Nov`. Find it in Settings > General > Status bar.

### Keyboard
- More responsive: fewer missed keys when typing fast.
- Slide your finger over the **space bar** to move the cursor: slide right and the cursor moves right, slide left and it moves left, following your finger.
- New symbol: `%`

### Translations
- The plugin is now translatable.
- Available in:
  - Español
  - Português (BR)

### Fixes
- Fixed a bug: tapping **Exit KOReader** now closes KOReader normally.
- New Home button 

## Installation
1. Download `KiKomeScrubber.koplugin.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `KiKomeScrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, use **Check for updates** in KiKome's Settings, or replace the folder. To uninstall, delete it.

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
