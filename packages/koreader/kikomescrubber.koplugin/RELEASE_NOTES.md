# v2.4.0 · 2026-11-21

## What's new

## Action center
A new first tab in KOReader's menu, available on Home and inside books. It is off by default: turn it on in **Settings > Actions > Action center**.

- **The book you're reading**: cover, title, author, progress and pages, with a pill showing the minutes left in the chapter. A round button next to it opens that book's Book details.
- **Your actions as round buttons**: icon-only circles in one row, next to the Library button (at the start on Home). If they don't all fit, a chevron appears and you can swipe the row, like the chips of Home.
- **Recent books**: swipe on the bottom part to get a second page with your recent books (without the one you're reading). Tap one to open it.
- **Hide / Show**: a button next to the book card hides KOReader's other menu tabs and brings them back when you tap it again. It works without restarting KOReader, and turning the Action center off brings the tabs back too.

### Manage your actions from Settings
**Settings > Actions** is now the one place where actions live. Make a new action (a KOReader action or a plugin, plus a name and an icon) and rename it, change its icon, change what it runs or delete it later. Each action can then be used in:
- **Home (Chip)**: the Actions chip of Home.
- **Action center**: the new first tab of KOReader's menu.

You can toggle any action on or off in each of the two places independently. In the Action center you can also choose where each action shows: **Show in Home** and **Show in documents** (inside the reader).

## New "Statistics" tab in Book details
A third tab next to Synopsis and Details, with the reading numbers of that one book:
- **Time read, Pages read and Reading days**, plus an estimated **Time left** when it can be worked out.
- **Last 7 days**: soft bars with today in black. Tap a day to see its minutes, tap again to go back to the week.
- Under the bars: **Daily average** and **Per page** (time per page).
- **First read** and **Last read** on one line, when there is room.
- Books with no statistics yet show a short message instead.

### Multiple "Top of Home" views
In **Settings > Home > Top of Home** you can now turn on more than one view (Recent books, Current book, Literary clock) and put them in the order you want. The first one is the default. On Home, swipe left or right over the top area to move between them. In Recent books, the swipe scrolls the covers first and then moves on to the next view.

## Fixes

### Plugin actions now show their on/off state
- FileBrowser, FileBrowser Plus, ZenFM and Tailscale actions now turn black when they are on, in the Actions chip, the Action center and the menu tab. Before, only Wi-Fi, night mode, the frontlight and the G-sensor did.

### "Minutes left in chapter"
in action center and top of home (current book), should always be correct.

## Performance and memory fixes for low-RAM devices
Fixes KiKome getting slower and slower on devices with little RAM (reported on a basic Kindle). Big books could take 20 to 40 seconds to open after a few books had been opened, and quitting KOReader took longer than usual.

- **Adaptive memory (new `kobold/data/memory.lua`).** KiKome reads the free RAM and sizes its cover cache accordingly, using less when memory is short.
- **When a book is about to open**, the cover cache is cut down and Lua's garbage is collected, so the book finds as much free memory as possible.
- **Shortly after the book is open**, if memory is still short, the KiKome screen parked under the book is released. It is rebuilt when the book is closed.
- **When you leave a book**, the cover cache gets its normal budget back.
- **Instant exit from books** (hot parking) is skipped automatically when memory is critical, so the book is fully closed and the next one starts with free memory.
- **Warm-up of other screens** is skipped when memory is short.
- **Home clock** no longer wakes up every minute while a book is open. It resumes when Home is painted again.


feedbacks are welcomed 


## Installation
1. Download `KiKomeScrubber.koplugin.zip` from the **Assets** section below (not "Source code").
2. Unzip it and copy the `KiKomeScrubber.koplugin` folder into `koreader/plugins/`.
3. Restart KOReader.

To update, use **Check for updates** in KiKome's Settings, or replace the folder. To uninstall, delete it.

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
