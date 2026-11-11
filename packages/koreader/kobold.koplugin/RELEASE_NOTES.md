# v2.0 · 2026-11-11

## Kobold 2.0

<!--kobold-->
Make Kobold yours: your own toolbar and nav bar with custom actions, Home widgets you can set up, live text on Home, and redesigned popups in the stock reader's style.
<!--/kobold-->

### New

- **Custom toolbar and nav bar**, add, remove and reorder items in Kobold Settings. Kobold opens on your first tab, and More always stays so you can't lock yourself out
- **Custom actions**, give any KOReader action or plugin a name and an icon (Kobold's, KOReader's, or your own SVG or PNG), then put it in the toolbar or nav bar
- **Home widgets**, show a series or collection of your choice in the My Books and collection stacks, and change what Continue Reading says, what tapping it does and the label under it
- **Live text on Home**, write your own stats or Continue Reading line with tokens like `[time]`, `[streak]`, `[battery]`, `[today_pages]` or `[book]`
- **Mark as finished, Mark as unread and Reset book** in the book menu. Reset asks first, just like KOReader
- **Natural light auto**, a switch in the brightness popup for KOReader's automatic warmth
- **Clock popup** with today's date, your reading time today, the date in the status bar and how soon the device goes to sleep
- **Battery popup** with the time left from KOReader's battery statistics and a link to the full stats
- **Translations**, Kobold's text can now be translated, other languages coming later

### Improved

- **Toolbar popups redesigned** in the stock reader's style. The icon gets a black circle while its popup is open, the box sits right under it, and there's a new on/off switch everywhere
- **Kobold's own popups everywhere**, choosing, confirming, typing, numbers and messages all use Kobold's style now, with an icon grid for picking icons
- **Press feedback**, tabs and list rows turn dark while you press them, like on the stock reader
- **Settings reorganised** into pages: Home, My Books, Toolbar, Nav bar, Custom actions and Opening books
- **New icons** for check for updates and natural light
- **Battery percentage** is shown inside the battery icon instead of making it wider

### Fixed

- Wi-Fi Settings showed an error when Wi-Fi was off. It now turns Wi-Fi on and shows your networks
- Settings changed right before a crash could be lost. Kobold now saves them straight away

### Install

1. Download `Kobold.koplugin.zip` below
2. Extract it and copy the `Kobold.koplugin` folder into KOReader's `plugins` folder
3. Restart KOReader and open Kobold, or set it under **Start with > Kobold Home**

On 1.1 or newer? Use **More > Check for updates** in Kobold.

To uninstall, delete the `Kobold.koplugin` folder and restart KOReader.

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
