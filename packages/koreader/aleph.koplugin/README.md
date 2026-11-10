# Aleph for KOReader

Your books, reading, highlights and shelves in one place: a customizable home screen, local library and reader tools for KOReader.

Aleph works with books and reading data on your device. No Aleph account or BookOrbit server is required. Optional author portraits use the internet; optional integrations can launch other plugins and their network features.

**This is a modified version of BookOrbit and is not an official BookOrbit release. Modified 9 November 2026.**

## Screenshots

<table>
  <tr>
    <td><img src="screenshots/home.png" alt="Home dashboard" width="260"></td>
    <td><img src="screenshots/book-details.png" alt="Book details" width="260"></td>
    <td><img src="screenshots/series.png" alt="Series reading order" width="260"></td>
  </tr>
  <tr>
    <td align="center">Home</td>
    <td align="center">Book details</td>
    <td align="center">Series</td>
  </tr>
  <tr>
    <td><img src="screenshots/authors.png" alt="Authors list with portraits" width="260"></td>
    <td><img src="screenshots/library-sort-filter.png" alt="Library sort and filter" width="260"></td>
    <td><img src="screenshots/top-menu-controls.png" alt="Top menu Controls tab" width="260"></td>
  </tr>
  <tr>
    <td align="center">Authors</td>
    <td align="center">Sort and filter</td>
    <td align="center">Top menu controls</td>
  </tr>
  <tr>
    <td><img src="screenshots/reader-menu.png" alt="Reader menu, This book" width="260"></td>
    <td><img src="screenshots/reader-menu-also-reading.png" alt="Reader menu, Also reading" width="260"></td>
    <td><img src="screenshots/bookmarks.png" alt="Bookmarks with filters" width="260"></td>
  </tr>
  <tr>
    <td align="center">Reader menu</td>
    <td align="center">Also reading</td>
    <td align="center">Bookmarks</td>
  </tr>
  <tr>
    <td><img src="screenshots/highlight-actions.png" alt="Highlight actions" width="260"></td>
    <td><img src="screenshots/highlight-style.png" alt="Highlight style and colour" width="260"></td>
    <td><img src="screenshots/highlight-colour-wheel.png" alt="Highlight colour wheel" width="260"></td>
  </tr>
  <tr>
    <td align="center">Highlight actions</td>
    <td align="center">Highlight style and colour</td>
    <td align="center">Custom colours</td>
  </tr>
  <tr>
    <td><img src="screenshots/pinned-picture.png" alt="Pinned picture drawer" width="260"></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td align="center">Pinned pictures</td>
    <td></td>
    <td></td>
  </tr>
</table>

## Installation

1. Download **aleph.koplugin.zip** from this repository's Releases page.
2. Extract it. Copy the entire **aleph.koplugin** folder into KOReader's `plugins` folder.
3. Check that `plugins/aleph.koplugin/main.lua` and `plugins/aleph.koplugin/_meta.lua` exist. Avoid an extra nested `aleph.koplugin` folder.
4. Restart KOReader. Open **Tools → Aleph**. If it is disabled, enable it in KOReader's Plugin management and restart.
5. In Aleph, open **Menu → Settings → Library folders → Add folder** and select your books folder. Subfolders are included. KOReader's Home folder is used initially when configured, and existing files in reading history are also indexed.
6. Let the first scan finish. Covers load as needed. Use **Menu → Refresh local library** after adding or transferring books.

The supplied project's documentation reports use with **KOReader 2026.07.1 on Kindle Paperwhite and Kindle Colorsoft**. Other versions and devices are not verified. Some controls require a touchscreen, frontlight, adjustable warmth or a color screen. No separate BookOrbit installation is required.

### Other plugins

- **Not compatible: ZenOS (Zen UI) and Simple UI.** Both put their own home screen over KOReader's file browser, as Aleph does (ZenOS also replaces the reader menus, page browser, dictionary and status bars). With either one enabled alongside Aleph, KOReader can slow down, freeze or crash, most often when a book is closed. Turn it off in Plugin management before using Aleph. Aleph shows a warning at startup when it finds one running.
- **Bookshelf** works alongside Aleph: the top bar's book details fall back to Bookshelf's page for books outside Aleph's library. Use one of them as the screen that opens at startup and after a book, not both, or they open one after the other.
- **Project: Title** and KOReader's Cover browser restyle the file browser that sits under Aleph's board; they work with Aleph. On devices with little memory, their list view uses less memory than the cover grid.
- **Menu restyling plugins** (Modern Menu, QuickUI, Reader Menu Redesign, Appearance and similar) restyle the same KOReader menus as Aleph. If you use one, turn off **Settings → Opening Aleph → Dialogs → Aleph dialogs** so the two do not fight over the same menus.
- The separate **Bookends** plugin: Aleph's book margins stay hidden while it is on.

## Home and dashboard

Four pages organize your reading: **Home, Insights, Library and Decor**. Swipe sideways or use the page controls to change pages.

Hold a dashboard widget, or choose **Settings → Home → Customize Home**. Select a widget and use **Earlier, Later, Size, Page, Remove** to arrange it; **Add widget** opens the available choices. Finish editing to save. Layouts are stored separately for screen column count and orientation.

Available widgets:

| Group | Choices |
|---|---|
| Reading | Continue reading, Also reading, Finish forecast, Highlight of the day, Word of the day |
| Statistics | Streak, This week, Today, Reading calendar, Year in reading, Goal pace, Reading records, When you read, Finished this year |
| Library | Pick back up, Want to read, Up next in series, Discover, Recently added; Library, Series, Authors, Collections, History and Search links |
| Device | Light, Quick settings, On device, Clock |
| Decor | Silverfish integration; reading companions; Chapter line, Gathering dust, Tree rings, Pages turned, Glyph of the day, Analog clock, Moon phase |

The 15 bundled reading companions are cat, dog, rabbit, owl, penguin, robot, vampire, dragon, ghost, mimic, mummy, witch, skeleton, candle and alien. They do not require Silverfish. The separate Silverfish widget does.

**Discover** shuffles your local books. **Want to read** uses unread books; **Pick back up** uses books in progress. These are local views, not separate online lists. **Recently added** reflects when Aleph first indexed the book. The annual goal counts indexed books marked Finished with a completion date in the current year. Chapter maps become available after opening and closing a book with Aleph installed.

## Settings reference

Open **Aleph → Menu → Settings**.

| Setting | What it changes | Initial behavior |
|---|---|---|
| Profile → Your name | Home greeting | Not set |
| Profile → Annual reading goal | Books to finish each year; 1–10,000 | 12 |
| Opening Aleph → When KOReader starts | Show file browser, or open Aleph when the file browser starts, including after closing a book | File browser |
| Opening Aleph → Shortcut | Pick an opening gesture; shows and confirms an existing binding before replacement | No Aleph shortcut assigned automatically |
| Opening Aleph → Dialogs → Aleph dialogs | Restyle opening cards, prompts, dictionary, highlights and many KOReader windows | On |
| Opening Aleph → Dialogs → Reader menu at the bottom | Aleph's reader menu instead of the stock bottom menu | On |
| Opening Aleph → Dialogs → Page browser on swipe up | Open Aleph's page browser from a bottom-edge swipe | On |
| Opening Aleph → Dialogs → Pinned pages | Position the badge and choose the drawer side | Bottom-right badge; right drawer |
| Top menu | Enable Controls and Apps tabs | On, unless standalone Quick Top Bar takes precedence |
| Top menu → Apps | Show/hide apps, change icons and arrange their order | Apps shown by default |
| Top menu appearance | Outline around icons, Controls/Apps tab icons; brightness/warmth sliders: Knob, Bar, Notched or Dots | Outline on; Knob sliders |
| Home → Starting layout | Reader, Stats or Library starting order; replaces customized pages after confirmation | Reader |
| Home → Tile style | Outline, Soft or Ink | Outline |
| Home → Colour | Accents, Tinted or Off; available on color-enabled screens | Accents; grayscale on monochrome screens |
| Home → Interface size | 1×, 1.05×, 1.1×, 1.15× or 1.2× | 1.05× |
| Home → Reset Home | Restore the selected starting layout and outline tiles | Confirmation required |
| Library folders | Add/remove roots, refresh or cancel a scan | Home folder if configured, plus reading history |
| Book margins | Enable header/footer statistics and customize their content | Enabled; both lines on |
| Author portraits | Enable online lookup, download all, stop downloading or remove downloaded portraits | Off |
| Help → About → Legal notices | Version, attribution and licensing information | Always available |

Turning **Aleph dialogs** off does not turn off the separate reader-menu, swipe-browser, top-menu or book-margin features. Change their own switches to restore those parts of KOReader. To disable all Aleph hooks, disable the plugin and restart KOReader.

## Library, authors and series

Use **List/Grid** to change the library view. Search matches title, author or series. The sort/filter sheet offers **Title, Author, Series, Added, Read**, reverse order, reading status, collection, genre and format. Choose **Done**, or tap outside the sheet, to apply. The main library remembers these choices; scoped author, series, genre and search views use their own current filters.

Title/author ordering has an A–Z index. Tap the pager for a letter jump or page selection. Authors and Series have their own List/Grid views, Name A–Z/Name Z–A/Most books sorting and reading/completion filters. Their preferences are remembered.

Genres come from book metadata, with adjacent Calibre `metadata.opf` subjects as a fallback. Calibre itself is not required.

Comic archives (CBZ, CBR, CB7, CBT) get their title, series and issue number, writers, genres and summary from the `ComicInfo.xml` inside them, which KOReader itself does not read. Metadata you set by hand in KOReader (**Book information → Set custom**) is used for every book.

Hold a book **in the library list or a series page** to select multiple books. Tap more books, then use **…** to change status, add to a collection, create a collection or select the whole displayed result set. Back exits the menu, then selection mode.

## Book details and highlights

Book details show the cover, title, author, series, rating, status, progress, description, genres and similar local books. Use Read/Resume to open it, swipe or tap neighboring titles to browse the current list, and tap series or genre links to explore related books.

- Tap a star to rate; tap the same star again to clear it.
- Tap status for **Unread, Reading, Finished or On hold**. These map to KOReader's new, reading, complete and abandoned statuses.
- Use **… → Add to collection** to manage membership in KOReader's own collections.
- **…** also offers Book information, Highlights and More by this author.
- **Read all** opens the full description; **+N** opens all genre tags.
- The Highlight of the day widget opens the full passage with chapter, date, note and a book-details link.

Aleph restyles highlight actions, selected-text actions, notes/details and the style/color picker. Hold a color name to rename it; hold a swatch to choose a replacement color. These names and colors affect KOReader globally. Drag the selection handles to adjust highlights in reflowable books; use the step arrows for PDFs. Holding an adjustment arrow switches between word and letter steps. Tap a highlight for Delete, Style, Note, Pin, Details and More; More has a Back button to return. In the dictionary pop-up, Highlight highlights the word and closes the pop-up.

## Reader tools

Tap the bottom menu region for **This book** and **Also reading**. This book links to Style, Contents, Bookmarks, Pages, the current-page bookmark switch, Book details and Aleph Home. With **BT Manager - HID Passthrough** installed, a small Bluetooth switch starts or stops its daemon; with **Syncery** installed, **Sync now** and **Progress** (its progress browser) sit beside it. Tap the Silverfish widget when its speech is cut short to read all of it. Also reading switches to another book in progress. X-Ray options appear when the optional X-Ray plugin is available.

Swipe up from the bottom edge for the page browser. It has Pages, Reading settings, Bookmarks, Highlights, Contents and Pinned pages tabs, a page carousel, grid, search and a slider. Tap the middle page to read there; tap side pages or swipe to browse. Hold a step arrow to skip a chapter. Close or Back returns without committing a page jump.

Bookmarks have All/Highlights/Bookmarks/Notes filters plus highlight style and color filters. The table-of-contents overlay also provides access to KOReader's native contents menu. Image viewing retains zoom and pan with Aleph's styled controls.

For reflowable documents, **Reading settings → Background** offers White, Paper, Sepia, Gray and Custom. The selected option is stored with the book; the custom color value is shared in Aleph's settings. A document's own painted background can override the appearance.

## Pinned pages and images

Hold selected text and choose **Pin**, or hold an image and choose **Pin image**. The badge opens a side drawer; hold it for the pin list. Drawer controls navigate, jump to the source page, remove pins, resize, zoom and open full screen. Pinch to zoom and drag to pan where supported. The newest pin also updates KOReader's own pinned-page location.

Use **Tools → Pin badge position** while reading, or **Settings → Opening Aleph → Dialogs → Pinned pages**, to choose one of eight positions, nudge the badge and select the drawer side.

## Book margins

Open **Settings → Book margins**, or **Tools → Book margins (top and bottom stats)** while reading. Enable/disable the feature, header and footer; select Small/Medium/Large text; choose no line, progress line or chapter-marked line; optionally hide KOReader's status bar. Choose the text colour (Light gray, Gray, Black, or any colour on a colour screen) and weight (Regular or Bold), and move the top and bottom lines nearer to or further from the edge of the screen. Tap each left/middle/right slot and select up to three items in order.

Items: progress, page, page of pages, pages left in chapter, time left in chapter/book, chapter, book title, author, clock, date, battery, Wi-Fi, frontlight and time read this sitting.

Defaults are progress/clock/battery on top and chapter time/session time/book time below, with a progress line and Small text. KOReader's status bar is not hidden by default. Aleph suppresses its margins when the separate Bookends plugin is active.

## Gestures and device controls

KOReader's gesture settings expose **Aleph: open**, **Aleph: this book**, **Aleph: page browser** and **Aleph: pinned pages**. The latter three are reader actions. The shortcut picker requires the Gestures plugin and offers top-left hold, bottom-right tap, two-finger top-right tap when supported, and top-right tap; the corner hold/top-right tap choices apply in books.

On Aleph pages, vertical swipes beginning in the left fifth adjust brightness; those in the right fifth adjust warmth where supported. A diagonal swipe performs a full e-ink refresh. Swipe down from the top edge for KOReader's top menu. Some gestures are suppressed while editing the dashboard.

Quick Top Bar adds Controls and Apps to the top menu. Controls include supported Wi-Fi, night mode, rotation, lighting, restart and exit actions. Apps launches available plugins; hold an app to hide it or change its icon. The current-book cover opens its details.

**Refresh distinction:** Menu/Settings → Refresh local library rescans local files. The dashboard Quick settings refresh action instead starts or requests a quick sync from **KOSyncthing+** when available; without it, the action rescans the library.

## Optional integrations

| Component | Purpose |
|---|---|
| KOReader Reading statistics | Collect reading time and provide the local statistics database; Aleph reads it without writing it |
| KOReader Vocabulary builder | Supplies saved lookup data for Word of the day |
| KOReader Gestures | Configure gesture shortcuts |
| Reading insights | Opens matching insight views from statistics widgets; native statistics views are the fallback |
| Silverfish 1.1.0 or newer | Supplies the optional Silverfish companion widget |
| X-Ray | Adds its available character, timeline, historical-figure, location, glossary, image/map and author tools |
| KOSyncthing+ | Optional start/quick-sync control; synchronization is performed by that plugin |
| Bookshelf | Optional book-details fallback for the current-book top-bar action |
| BT Manager - HID Passthrough | A Bluetooth switch in the reader menu |
| Syncery | Sync now and its progress browser in the reader menu |

The standalone **Quick Top Bar** takes precedence over Aleph's built-in top bar. Choose which implementation to use. Other plugins or patches that replace the same reader menus, highlight panels or top menu can conflict; their combinations have not all been tested.

## Network use and stored data

Ordinary library/dashboard browsing requires no server. Author portraits are off initially. When enabled, Aleph searches Open Library, then English Wikipedia, and downloads matching images from the returned image URLs. Requests include author search text and normal connection metadata. Images are cached locally; failed lookups are retried after 30 days. Bulk lookup can be stopped. Lookup requests can temporarily delay the interface on a slow connection.

Attribution links open only when selected. Dictionary/Wikipedia/translation and third-party plugin actions retain their own network behavior. Aleph has no BookOrbit login, API synchronization or self-updater; Storefront can manage plugin updates.

Aleph stores:

- `settings/aleph_index.lua`: rebuildable library metadata, device paths and highlight excerpts.
- KOReader's `aleph` settings table: preferences, layouts, margins, pin presentation and custom highlight palette. Aleph applies that palette to KOReader's shared highlight tables while active.
- KOReader's `quicktopbar` settings table: launcher icons, order, visibility and appearance.
- `cache/aleph/`: covers, generated art/icons, chapter maps, portraits and saved pinned images.
- KOReader book settings: user-requested rating/status changes, pins and background options. Collection and annotation actions use KOReader's own data mechanisms. Global highlight names/colors and gesture choices also modify their respective KOReader settings.

The library index is device-specific; build it separately on each device. Use Syncthing independently and refresh the local library after transfers finish. Removing an indexed folder does not delete books; history entries can still include existing books from that location. Cancelling a scan or encountering an unreadable root preserves the previous index; individual unreadable books retain a previous entry when available.

**Do not indiscriminately delete `cache/aleph/`: pinned image files live there.** Back up book sidecars, KOReader settings and pinned image files before reset/migration. Update by replacing the plugin folder with the new release and restarting. Disabling/removing the plugin does not automatically erase its saved preferences, gesture bindings or book-data changes.

## Troubleshooting and reports

For missing books, check folder selection and filters, then refresh. For empty time statistics, enable KOReader's Reading statistics and collect reading data. For visual conflicts, switch off the affected Aleph feature and restart if needed. Freezes when closing a book usually mean another home screen plugin, such as ZenOS or Simple UI, is running too: turn it off first. Include your device model, KOReader version, Aleph version, reproduction steps and relevant `crash.log` lines in an issue. Review logs for private file paths before sharing.

## Credits and license

[Powered by BookOrbit](https://github.com/bookorbit/bookorbit).

Copyright (C) 2025–2026 neon. Additional copyright is held by the respective BookOrbit contributors.

Licensed under the GNU Affero General Public License, version 3 only, with additional terms. This software is provided without warranty. You may redistribute and modify it under those terms.

Preserve `LICENSE`, `ADDITIONAL_TERMS.md`, `NOTICE`, `MODIFICATIONS.md`, `THIRD_PARTY_NOTICES.md`, `ZENOS_NOTICE.md` and `LICENSE-GPL-3.0.md` with the plugin. The package includes attribution for BookOrbit, ZenOS, Lucide/Feather and Bookends-related design. Complete Lua runtime source is included in the plugin folder; release tags identify the published version.
