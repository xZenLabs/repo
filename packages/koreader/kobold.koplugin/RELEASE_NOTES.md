# v1.5 · 2026-11-02

## Kobold 1.5

<!--kobold-->
Remove books from Home or bring them back, new nav bar icons that fill in when selected, a status bar that keeps the time current, and a lot of fixes under the hood.
<!--/kobold-->

### New

- **Remove from Home**, hold one of the books on Home to take it off the reading row. Its progress, status and collections stay as they are, and it comes back on its own when you open it again
- **Show in Home**, in a book's "..." menu in My Books, for books you're reading that aren't on Home. Puts the book first on the reading row
- **New nav bar icons**, thin outlines that fill in when their tab is selected, closer to the stock look

### Improved

- **Clock** in the status bar now updates every minute and right after waking the device, with Wi-Fi and battery updating along with it
- **View switch** on Books and Series now uses Kobold's own dropdown, showing just the view to switch to: Cover view or List view
- **Restart Kobold** now fully reloads Kobold
- **Nav bar labels and file sizes** can now be translated

### Fixed

- Tapping an empty spot on Home's reading row could open a book that was no longer there
- Changes made from the book menu could leave My Books reloading after it was closed
- Errors reading book data or reading stats are now written to KOReader's log instead of failing silently

### Under the hood

- **My Books split up**, `mybooks.lua` was ~1700 lines. The screen itself stays in `kobold/ui/mybooks.lua`, with rows and grid, collections, and the Files tab moved to `kobold/ui/mybooks/`. No change in behaviour
- **One hook for the file browser's refresh** (`kobold/ui/hooks.lua`), so screens listening to book menu changes can't stack up
- **Shared line height helper**, screens no longer measure text by hand

### Install

1. Download `Kobold.koplugin.zip` below
2. Extract it and copy the `Kobold.koplugin` folder into KOReader's `plugins` folder
3. Restart KOReader and open Kobold, or set it under **Start with > Kobold Home**

On 1.1 or newer? Use **More > Check for updates** in Kobold.

To uninstall, delete the `Kobold.koplugin` folder and restart KOReader.

# v1.4 · 2026-10-28

## Kobold 1.4

<!--kobold-->
A new search page, collections that work like the stock reader, Add to collection in the book menu, and finer brightness steps.
<!--/kobold-->

### New

- **Search page**, search your books by title, author or series, with recent searches, sort options and pages
- **New collection** from the "..." on the Collections tab, name it and pick its books straight away
- **Manage collection**, add and remove books in one place, with filter, sort and search. Nothing changes until you save
- **Collection menu**, hold a collection to manage, rename or delete it
- **Filter, sort and cover view inside a collection**, remembered for each collection
- **Add to collection** in the book menu, tick the collections a book belongs to
- **Toolbar settings**, choose Kobold's search or KOReader's search, and set how much each brightness tap changes the light

### Improved

- **Brightness and natural light** now step by 1% per tap instead of 10%
- **Collections list** shows the book count beside each collection
- **About page** now links to the source code and Ko-fi
- **Menus** open beside the "..." you tapped, with an arrow pointing at it

### Install

1. Download `Kobold.koplugin.zip` below
2. Extract it and copy the `Kobold.koplugin` folder into KOReader's `plugins` folder
3. Restart KOReader and open Kobold, or set it under **Start with > Kobold Home**

On 1.1 or newer? Use **More > Check for updates** in Kobold.

To uninstall, delete the `Kobold.koplugin` folder and restart KOReader.

# v1.3 · 2026-10-23

## Kobold 1.3

<!--kobold-->
A new book menu and book details page, filter, sort and search when adding books to a collection, an icon style option, and fixes for the Series scrollbar and cover outlines.
<!--/kobold-->

### New

- **Book menu**, tap the "..." on a book in My Books for Read now, View Details and KOReader Details. Hold any of the 4 recent books on Home for the same menu
- **Book details page** with the cover, series, author and progress, a Read now button, and Synopsis and Details tabs
- **Add books to a collection** now has filter, sort and search, tap the search pill to go back to the full list
- **Book menu setting**, use Kobold's menu or go straight to KOReader's book menu
- **Icons setting**, use Kobold's icons or KOReader's default icons for the status bar and nav bar

### Fixed

- **Series scrollbar** no longer jumps to the middle when only one series is left on a page
- **Cover outlines** now sit right on the cover with no gap
- **Italic text** in menus and settings uses a proper italic font instead of a wide one

### Install

1. Download `Kobold.koplugin.zip` below
2. Extract it and copy the `Kobold.koplugin` folder into KOReader's `plugins` folder
3. Restart KOReader and open Kobold, or set it under **Start with > Kobold Home**

On 1.1 or newer? Use **More > Check for updates** in Kobold.

To uninstall, delete the `Kobold.koplugin` folder and restart KOReader.

# v1.2 · 2026-10-21

## Kobold 1.2

<!--kobold-->
Instant return after closing a book, new icons, redesigned popups and settings, a Wi-Fi switch, and a cleaner Series tab.
<!--/kobold-->

### New

- **Instant return** after closing a book, with no flash of KOReader's file browser
- **Opening and closing panel**, an optional "Opening Book" / "Closing Book" panel instead of KOReader's messages. Off by default, turn it on in Settings 
- **Wi-Fi switch** in the Wi-Fi popup to turn Wi-Fi on or off, plus a Wi-Fi Settings link to pick a network
- **Book menu on Home**, hold any of the 4 recent books for the same menu as the "..." in My Books
- **Setting tooltips**, tap a setting's name to see what it does

### Improved

- **New icons** for the status bar and navigation bar, white on black in night mode
- **Popups** have square corners and an arrow pointing at the icon that opened them
- **Settings** is a compact panel that fits more per page, with a page bar on the side
- **About** is now a panel like Settings
- **Series tab** shows the author and book count, with a small stack above the cover for series with more than one book
- **Battery** shows its charge level while charging, with the lightning bolt on top
- **Home** keeps the same collection and covers instead of changing them every time you close a book

### Install

1. Download `Kobold.koplugin.zip` below
2. Extract it and copy the `Kobold.koplugin` folder into KOReader's `plugins` folder
3. Restart KOReader and open Kobold, or set it under **Start with > Kobold Home**

On 1.1 or newer? Use **More > Check for updates** in Kobold.

To uninstall, delete the `Kobold.koplugin` folder and restart KOReader.

# v1.1.1 · 2026-10-17

## Kobold 1.1.1

<!--kobold-->
Fixes the search button in the status bar.
<!--/kobold-->

### Fixed

- **Search button** in the status bar works again. Taps on Kobold's own buttons near a screen corner no longer trigger KOReader corner gestures

### Install

1. Download `Kobold.koplugin.zip` below
2. Extract it and copy the `Kobold.koplugin` folder into KOReader's `plugins` folder
3. Restart KOReader and open Kobold, or set it under **Start with > Kobold Home**

On 1.1 already? Use **More > Check for updates** in Kobold.

To uninstall, delete the `Kobold.koplugin` folder and restart KOReader.
