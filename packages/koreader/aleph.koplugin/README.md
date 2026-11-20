# Aleph for KOReader

Your books, reading, highlights and shelves in one place: a customizable home screen, local library and reader tools for KOReader.

Aleph works with books and reading data on your device. No Aleph account or BookOrbit server is required. Optional author portraits use the internet; optional integrations can launch other plugins and their network features.

**This is a modified version of BookOrbit and is not an official BookOrbit release. Modified 20 November 2026.**

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
5. In Aleph, open **Menu → Settings → Library → Add folder** and select your books folder. Subfolders are included. KOReader's Home folder is used initially when configured, and existing files in reading history are also indexed.
6. Let the first scan finish. Covers load as needed. Use **Menu → Refresh local library** after adding or transferring books.

The supplied project's documentation reports use with **KOReader 2026.07.1 on Kindle Paperwhite and Kindle Colorsoft**. Other versions and devices are not verified. Some controls require a touchscreen, frontlight, adjustable warmth or a color screen. No separate BookOrbit installation is required.

### Other plugins

- **Not compatible: ZenOS (Zen UI) and Simple UI.** Both put their own home screen over KOReader's file browser, as Aleph does (ZenOS also replaces the reader menus, page browser, dictionary and status bars). With either one enabled alongside Aleph, KOReader can slow down, freeze or crash, most often when a book is closed. Turn it off in Plugin management before using Aleph. Aleph shows a warning at startup when it finds one running.
- **Bookshelf** works alongside Aleph: the top bar's book details fall back to Bookshelf's page for books outside Aleph's library. Use one of them as the screen that opens at startup and after a book, not both, or they open one after the other. When you ask for Aleph (Aleph Home in the reader menu, the "Aleph: open" gesture, its menu item or tab) after reading a book opened from Bookshelf, Aleph stays on top: Bookshelf's screen, which puts itself back when that book closes, is closed as its own "Bookshelf: open or close" does.
- **Project: Title** and KOReader's Cover browser restyle the file browser that sits under Aleph's board; they work with Aleph. On devices with little memory, their list view uses less memory than the cover grid.
- **Menu restyling plugins** (Modern Menu, QuickUI, Reader Menu Redesign, Appearance and similar) restyle the same KOReader menus as Aleph. If you use one, turn off **Settings → Home → Aleph dialogs** so the two do not fight over the same menus.
- The separate **Bookends** plugin: Aleph's book margins stay hidden while it is on.

## Home and dashboard

Four pages organize your reading: **Home, Insights, Library and Decor**. Swipe sideways or use the page controls to change pages.

Hold a dashboard widget, or choose **Settings → Home → Customize Home**. Select a widget and use **Earlier, Later, Size, Page, Colour, Remove** to arrange it (Colour, on a colour screen: the widget's own colour or one of eleven others, for that widget only); **Add widget** opens the available choices. Finish editing to save. Layouts are stored separately for screen column count and orientation.

Available widgets:

| Group | Choices |
|---|---|
| Reading | Continue reading, Also reading, Finish forecast, Highlight of the day, Word of the day |
| Statistics | Streak, This week, Today, Reading calendar, Year in reading, Goal pace, Goals, Daily goal, Weekly goal, Monthly goal, Reading DNA, Monthly challenge, Reading rhythm, Year projection, Hours read, Time read, Books and pages, Diversity score, Reading bingo, Reading records, When you read, Finished this year |
| Library | Pick back up, Want to read, Up next in series, Discover, Recently added; Library, Series, Authors, Collections, History and Search links |
| Device | Light, Quick settings, On device, Clock, Weather |
| Decor | Silverfish integration; reading companions; Chapter line, Gathering dust, Tree rings, Pages turned, Glyph of the day, Analog clock, Literary clock, Moon phase |

The 15 bundled reading companions are cat, dog, rabbit, owl, penguin, robot, vampire, dragon, ghost, mimic, mummy, witch, skeleton, candle and alien. They do not require Silverfish. The separate Silverfish widget does.

**Discover** shuffles your unread books, and offers only the next book to read in each series. **Want to read** uses unread books; **Pick back up** uses books in progress. These are local views, not separate online lists. **Recently added** reflects when Aleph first indexed the book. The annual goal counts indexed books marked Finished with a completion date in the current year. The **Goals** widget shows four goals together: minutes read today, days read this week, books finished this month and this year, each as done / goal with a bar and a check once it is met; tap it to set them. **Daily goal**, **Weekly goal** and **Monthly goal** show one each, larger, with what is left ("18 min to go", "2 days to go", "1 book to go · 12 days left"); the weekly one also has the week's days as dots, filled on the days you read. The yearly goal has Goal pace. **Reading DNA** (after BookOrbit's widget) names the kind of reader you are ("Rapid Explorer", "Deep Specialist"…) from five traits shown as bars: Length (how long your finished books are), Variety (genres per book), Rhythm (how many of the last 182 days you read), Time (the hour you read most) and Speed (pages an hour); it appears once five books are finished. Four more after BookOrbit's: **Monthly challenge** picks one challenge a month that suits how you read (Quick Read, Genre Explorer, Clear the Backlog, Streak Builder, New Voice, Page Turner) and shows how far along you are; **Reading rhythm** shows the last 14 days as bars, with the days you read, your consistency and your average a day; **Year projection** says where the last 30 days' pace takes you by the end of the year, in books, pages and hours, trending up or down; **Diversity score** rates how widely you read from genres, authors, eras (with the extra filters on) and languages, once three books are finished. **Hours read** shows all the hours read on this device, since when, this year's and the books they went to. Two charts after the Reading Log plugin's, as wide as Year in reading: **Time read**, this year's hours month by month as bars, and **Books and pages**, the books finished and pages read each month as two lines. Chapter maps become available after opening and closing a book with Aleph installed.

**Weather.** A Device widget (Customize → + Add widget → Device) with the temperature now, the sky in words and an icon, and today's high and low; a wide tile adds the next two days. Tap it to choose your town, switch °C/°F or update now. It never turns Wi-Fi on: it updates only when Home is shown with Wi-Fi already connected, at most once an hour, in the background, and otherwise shows the last forecast. Forecasts come from [Open-Meteo](https://open-meteo.com) (free, no account); only the town's position is sent.

**Literary clock.** A Decor widget (Customize → + Add widget → Decor) that tells the time with a line from a book that mentions it: the quote for the current minute, the time in bold, the book's title and author under it, at the largest size that fills the tile. When a minute has several quotes the choice changes from day to day. Quotes the collection marks as not safe for work are left out; the few minutes with no quote show a line written like one, with the time in words. It changes each minute while Home is on screen. The quotes come from the Literature Clock collection (The Guardian's readers, JohannesNE, Carlos Bonadeo), as converted by readinpixels' Literary Clock plugin, and are shared under CC BY-NC-SA 2.5 (see THIRD_PARTY_NOTICES.md).

**Wallpaper.** Customize Home → **+ Add wallpaper** puts a picture from your device behind every page of Home (the picker opens in an `images` folder at the root of the device, such as `/mnt/us/images` on a Kindle, then in the folder you last chose from), with its fit, how faded it is and how see-through the widgets are. **Text over the wallpaper** sets the colour of Home's own text (the greeting, date, status and buttons at the top, the page dots and name at the foot): Auto picks dark or light from how light the picture is behind each of them, or choose Dark or Light; **Outline** adds an edge in the other colour, for a busy picture. Seven seasonal wallpapers made for Aleph, at the Kindle Colorsoft's size (Three Kings, Valentine, St Patrick's Day, Easter, Summer, Autumn, Christmas), are in the [wallpapers folder](wallpapers/), or all together as **aleph-wallpapers.zip** on the Releases page.

**Owner information.** Menu → Owner information: your name, email and phone number, shown large under "If you find this e-reader, please contact:", so whoever finds a lost device can reach you. Kept on the device only.

## Settings reference

Open **Aleph → Menu → Settings**.

| Setting | What it changes | Initial behavior |
|---|---|---|
| Profile → Your name | Home greeting | Not set |
| Profile → Annual reading goal | Books to finish each year: − and + or tap the number to type one (1–100,000) | 12 |
| Profile → Goals widget | Daily goal (minutes), Weekly goal (days read, the week starting on KOReader's calendar's first day), Monthly goal (books finished); 0 turns one off and the Goals widget leaves it out | 30 min; 5 days; 2 books |
| Opening Aleph → When KOReader starts | Show file browser, or open Aleph when the file browser starts, including after closing a book | File browser |
| Opening Aleph → Shortcut | Pick an opening gesture; shows and confirms an existing binding before replacement | No Aleph shortcut assigned automatically |
| Home → Aleph dialogs | Restyle opening cards, prompts, dictionary, highlights and many KOReader windows | On |
| Reader → Reader menu at the bottom | Aleph's reader menu instead of the stock bottom menu | On |
| Reader → Page browser on swipe up | Open Aleph's page browser from a bottom-edge swipe | On |
| Reader → Pinned pages | Position the badge and choose the drawer side | Bottom-right badge; right drawer |
| Reader → Choose a colour when bookmarking | Show the list of bookmark colours when a page is bookmarked; bookmarks appear as a ribbon in their colour | On; Blue first, then the colour used last |
| Reader → Search like a Kindle | Every search result on a page of its own, a bar to go through them, and a way back to the page you were reading | On |
| Reader → Way back after a jump | After the contents, Go to page, a link, a bookmark or a pin: "Go to most recent page" at the foot of the page | On |
| Top menu | Enable Controls and Apps tabs | On, unless standalone Quick Top Bar takes precedence |
| Top menu → Apps | Show/hide apps, change icons and arrange their order | Apps shown by default |
| Top menu appearance | Outline around icons, Controls/Apps tab icons, the Wi-Fi tile's icon (holding that tile lists the Wi-Fi networks in range, as in KOReader); brightness/warmth sliders: Knob, Bar, Notched or Dots | Outline on; Knob sliders |
| Top menu → Font, Text size | The top menu's own font (or the same as Home), and its size, 80% to 150%: the whole menu with its icons and tabs | Same as Home; 100% |
| Home → Starting layout | Reader, Stats or Library starting order; replaces customized pages after confirmation | Reader |
| Home → Tile style | Outline, Soft or Ink | Outline |
| Home → Colour | Accents, Tinted or Off; available on color-enabled screens | Accents; grayscale on monochrome screens |
| Home → Interface size | 1× to 1.5× (1, 1.05, 1.1, 1.15, 1.2, 1.25, 1.3, 1.4, 1.5), with − and + | 1.05× |
| Home → Font | The font of Home, its widgets, the library and Aleph's windows: any of KOReader's fonts, each name shown in its own font (quotes keep Noto Serif) | Noto Sans |
| Customize Home → Add wallpaper | A picture behind the widgets, with fit, wallpaper opacity, widget opacity, and the colour of Home's text over it (Auto, Dark, Light; Outline) | No wallpaper |
| Home → Night profile | Night light (brightness, warmth) and bolder book text while night mode is on; your day light back after | Off |
| Home → Night profile → By the clock | Night mode on and off by itself between two times | Off; 21:00–07:00 |
| Home → Reset Home | Restore the selected starting layout and outline tiles | Confirmation required |
| Library | Add/remove folders, refresh or cancel a scan, cover shape, extra filters, Import from Goodreads, Goodreads sign-in, Keep Goodreads up to date (Track every book, Send the percentage, Send the stars, Waiting to send) | Home folder if configured, plus reading history |
| Book margins | Enable header/footer statistics and customize their content | Enabled; both lines on |
| Author portraits | Enable online lookup, download all, stop downloading or remove downloaded portraits | Off |
| Library → Collections from Calibre | Puts books in the KOReader collections named in Calibre's #collections column (see below) | On |
| Library → Goodreads sign-in | Says Signed in or Not signed in; tapped, listens on the local network for a few minutes so the Aleph Goodreads cookie browser extension can send goodreads.com cookies (see below) | Not listening |
| Menu → Owner information | Your name, email and phone, shown to whoever finds a lost device | Not set |
| Help → About → Legal notices | Version, attribution and licensing information | Always available |

Turning **Aleph dialogs** off does not turn off the separate reader-menu, swipe-browser, top-menu or book-margin features. Change their own switches to restore those parts of KOReader. To disable all Aleph hooks, disable the plugin and restart KOReader.

## Library, authors and series

Use **List/Grid** to change the library view. Search matches title, author or series. The sort/filter sheet offers **Title, Author (by first or last name), Series, Added, Read** (and **Progress** when showing Reading: most or least read first), reverse order, reading status, collection, genre and format. Choose **Done**, or tap outside the sheet, to apply. The main library remembers these choices; scoped author, series, genre and search views use their own current filters.

Title/author ordering has an A–Z index. Tap the pager for a letter jump or page selection. Authors and Series have their own List/Grid views, Name A–Z/Name Z–A/Most books sorting and reading/completion filters. Their preferences are remembered.

Genres come from book metadata, with adjacent Calibre `metadata.opf` subjects as a fallback. Calibre itself is not required.

Comic archives (CBZ, CBR, CB7, CBT) get their title, series and issue number, writers, genres and summary from the `ComicInfo.xml` inside them, which KOReader itself does not read. Metadata you set by hand in KOReader (**Book information → Set custom**) is used for every book.

Hold a book **in the library list or a series page** to select multiple books. Tap more books, then use **…** to change status, add to a collection, create a collection or select the whole displayed result set. Back exits the menu, then selection mode.

## Book details and highlights

Book details show the cover, title, author, series, rating, status, progress, description, genres and similar local books. Use Read/Resume to open it, swipe or tap neighboring titles to browse the current list, and tap series or genre links to explore related books.

- Tap a star to rate: the left half of a star gives a half star, the right half a whole one. Tap the same rating again to clear it. KOReader's own screens show the whole stars (4 for 4.5).
- Tap status for **Unread, Reading, Finished or On hold**. These map to KOReader's new, reading, complete and abandoned statuses.
- Use **… → Add to collection** to manage membership in KOReader's own collections.
- **…** also offers Book information, Highlights, More by this author, and **Delete book**, with two ways to do it: **Delete book, keep its data** (only the file; highlights, progress and status stay in its sidecar) or **Delete book and its data** (the file and its sidecar). Each asks first; reading statistics are kept either way.
- **Read all** opens the full description; **+N** opens all genre tags.
- The Highlight of the day widget opens the full passage with chapter, date, note and a book-details link.

Aleph restyles highlight actions, selected-text actions, notes/details and the style/color picker. Hold a color name to rename it; hold a swatch to choose a replacement color. These names and colors affect KOReader globally. Drag the selection handles to adjust highlights in reflowable books; use the step arrows for PDFs. Holding an adjustment arrow switches between word and letter steps. Tap a highlight for Delete, Style, Note, Pin, Details and More; More has a Back button to return. In the dictionary pop-up, Highlight highlights the word and closes the pop-up.

## Reader tools

Tap the bottom menu region for **This book** and **Also reading**. This book links to Style, Search, Bookmarks, Pages (tap the Chapter line for the table of contents), the current-page bookmark switch, Book details and Aleph Home. With **BT Manager - HID Passthrough** installed, a small Bluetooth switch starts or stops its daemon; on a Kobo with the **Kobo plugin** (kobo.koplugin) and a model it supports Bluetooth on (Libra 2, MTK models), the switch turns the Kobo's Bluetooth on and off through that plugin instead; with **Syncery** installed, **Sync now** and **Progress** (its progress browser) sit beside it. Tap the Silverfish widget when its speech is cut short to read all of it. Also reading switches to another book in progress. X-Ray options appear when the optional X-Ray plugin is available.

Swipe up from the bottom edge for the page browser. It has Pages, Reading settings, Bookmarks, Highlights, Contents and Pinned pages tabs, a page carousel, grid, search and a slider. Tap the middle page to read there; tap side pages or swipe to browse. Hold a step arrow to skip a chapter. Close or Back returns without committing a page jump.

Bookmarks have All/Highlights/Bookmarks/Notes filters plus highlight style and color filters. The table-of-contents overlay also provides access to KOReader's native contents menu. Image viewing retains zoom and pan with Aleph's styled controls.

For reflowable documents, **Reading settings → Background** offers White, Paper, Sepia, Gray and Custom. The selected option is stored with the book; the custom color value is shared in Aleph's settings. A document's own painted background can override the appearance.

**Search like a Kindle.** Search a book (the page browser's search button, KOReader's search gesture, or Search on selected text) and every match shows on a page of its own, with an Annotations tab for highlights and notes that hold the words, and a Text tab with two lines around each match, its chapter and page. Tap one to read it there: the word is highlighted and a bar at the foot of the page shows the page and ‹ Result 3 of 46 ›; tap "Result 3 of 46" for the list again, × to finish. When you finish away from the page you were reading, **Go to most recent page** takes you back, and **Return to page …** returns. Hold the search button on the results page for KOReader's own search box (case, whole words, regular expressions). **Settings → Reader → Search like a Kindle** turns it off.

## X-Ray

Aleph's own X-Ray lists the people, places and other names of the book you are reading, and where each was mentioned **up to the page you are on**. It is off until you turn it on in **Settings → X-Ray**; while off, none of it is loaded. It works with books KOReader lays out itself (EPUB and the like), not with PDFs or comics.

- **First use in a book:** open the reader menu → **This book → X-Ray → Find names in this book**. The book is read once in the background (a minute or two; you can keep reading) and a note says when it is done. Nothing is sent anywhere: names are found from capital letters in the text.
- **Opening it:** the X-Ray row in **This book**; the **X-Ray** button after selecting a word; the gesture **Aleph: X-Ray**; or a tap on an underlined name.
- **A name's card:** its other spellings, how many times it was mentioned so far, **where it comes up** (a bar for each chapter read, with the chapter it was first seen in, the one with most mentions and the latest), the names **often with** it (tap one to open it), and each mention with its page, chapter and the words around it. All of this is worked out on the device, with no AI. Tap a mention to go there; KOReader's back gesture returns. **Not a name** hides a wrong entry.
- **Underline names** (off by default): a thin line under each name on the page. This is the only part that does any work as pages turn; turn it off if page turns feel slower.
- **Show the whole book** (off by default): also lists names and mentions from pages you have not read.
- **Descriptions with AI** (optional): add your own key for Claude, OpenAI, Gemini or another OpenAI-style service in **Settings → X-Ray**, then tap **Describe with AI** in a book's X-Ray. One request sends the book's title and author, how far you are, and two short excerpts per name from the pages already read. The answer adds what each name is and the People / Places / Other filters. Ask again later in the book to update. **Detailed descriptions** (Settings → X-Ray, off by default, for an AI account with a larger allowance) gives the 15 most mentioned names 3–4 sentences each (who they are, their role, relationships and what they have done so far), written from eight longer passages each, the names often near them, and the Story's chapter summaries when there are any. That question is several times longer, so it uses several times more of your allowance; still nothing after the page you are on is sent. The model name can be changed in Settings; the defaults may need updating as providers rename theirs. The key is stored as typed in KOReader's settings file.

- **Story** (optional, needs the same key): the **Story** tab of a book's X-Ray. **Update the story** sends the text of the chapters you have read, and nothing after the page you are on, to the provider; it comes back as a short summary of each chapter and "the story so far". It runs in the background and you can keep reading. Later updates only send what you have read since. Tap a chapter to read its summary whole or go to it; the ‹ › buttons beside The story and Go to chapter (or a sideways swipe) move to the summaries around it.
- **The book before:** for a book that is part of a series (not its first), the Story tab has **The book before**. If that book is in your library and has a Story of its own on this device, the recap is written from those chapter summaries. Otherwise the model is asked what it knows of the book from its title alone, and the answer is marked as such, since it can be wrong.
- **After a break:** when you open a book you have not read for a while (2 weeks unless changed in **Settings → X-Ray → Offer a recap after a break**: 1 week, 2 weeks, 1 month or Never), or one whose status was On hold, Aleph asks once whether you want the story so far. Nothing is sent unless you say yes.

The name finder is simple: it will miss some names and list a few words that are not names. X-Ray's files (`aleph_xray*.lua`) sit in the book's settings folder next to its highlights.

## Pinned pages and images

Hold selected text and choose **Pin**, or hold an image and choose **Pin image**. The badge opens a side drawer; hold it for the pin list. Drawer controls navigate, jump to the source page, remove pins, resize, zoom and open full screen. Pinch to zoom and drag to pan where supported. The newest pin also updates KOReader's own pinned-page location.

Use **Tools → Pin badge position** while reading, or **Settings → Reader → Pinned pages**, to choose one of eight positions, nudge the badge and select the drawer side.

## Book margins

Open **Settings → Book margins**, or **Tools → Book margins (top and bottom stats)** while reading. Enable/disable the feature, header and footer; select Small/Medium/Large text; choose no line, progress line or chapter-marked line; optionally hide KOReader's status bar. Choose the text colour (Light gray, Gray, Black, or any colour on a colour screen) and weight (Regular or Bold), and move the top and bottom lines nearer to or further from the edge of the screen. Tap each left/middle/right slot and select up to three items in order.

Items: progress, page, page of pages, pages left in chapter, time left in chapter/book, chapter, book title, author, clock, date, battery, Wi-Fi, frontlight and time read this sitting.

Defaults are progress/clock/battery on top and chapter time/session time/book time below, with a progress line and Small text. KOReader's status bar is not hidden by default. Aleph suppresses its margins when the separate Bookends plugin is active.

**Page turner battery.** With the BT Manager / HID Passthrough plugin and a Bluetooth page turner, the bottom line of a book's page ends with a dot, the Bluetooth mark and the page turner's battery (" · 80%"), after whatever its right-hand side shows. It appears only while a page turner reports its battery, and shows up with the first page it turns. Settings → Book margins → Page turner battery turns it off. The daemon is asked in the background, so a slow answer never holds up a page; without HID Passthrough installed nothing is asked at all. The lines are redrawn each minute only when something on them changed (a clock, the battery dropping a point), so lines without a clock cost no refresh while you read.

## Gestures and device controls

KOReader's gesture settings expose **Aleph: open**, **Aleph: this book**, **Aleph: page browser** and **Aleph: pinned pages**. The latter three are reader actions. The shortcut picker requires the Gestures plugin and offers top-left hold, bottom-right tap, two-finger top-right tap when supported, and top-right tap; the corner hold/top-right tap choices apply in books.

On Aleph pages, vertical swipes beginning in the left fifth adjust brightness; those in the right fifth adjust warmth where supported. A diagonal swipe performs a full e-ink refresh. Swipe down from the top edge for KOReader's top menu. Some gestures are suppressed while editing the dashboard.

Quick Top Bar adds Controls and Apps to the top menu. Controls include supported Wi-Fi, night mode, rotation, lighting, restart and exit actions. Apps launches available plugins; hold an app to hide it or change its icon. The current-book cover opens its details.

**Night profile.** Settings → Home → Night profile. When night mode turns on, the front light changes to your night brightness and warmth, and book text gets a little bolder so light letters on black stay crisp; when night mode turns off, your day light comes back. Choose the night brightness and warmth (or take the light as it is now), whether changes made at night are remembered, and how much bolder the text gets. Under By the clock, night mode can turn on and off by itself between two times (21:00 to 07:00 by default); switch it by hand and it stays that way until the next change. If you use the 2-night-profile.lua patch, delete it from koreader/patches first: Aleph's profile stays off while the patch is there.

**Finished books are remembered.** Aleph keeps a record of every book you finish, so deleting a book after reading it does not take it off your yearly count or the Finished this year shelf. Tap a deleted book there to see when you finished it, or to remove it from the record.

**Page-turn buttons** (Kobo Libra, Kindle Oasis, a keyboard) turn the Home pages and the library's pages. **Direction keys** (a Kindle 4, a keyboard Kindle): Up, Down, Left and Right move a mark between everything that can be tapped on Home, in the library, on a book's page and in Aleph's panels and menus, and Press taps it; past the left or right edge Home turns its page. This is on by itself on devices with those keys, and **Settings → About → Button navigation** turns it on elsewhere (reopen Home after). It is new in 1.1.46 and has not been tried on a button-only device yet. **Settings → Library → Covers** draws every cover at its own shape (Whole), or all the same size, trimmed (Fill) or stretched (Stretch).

**Widget actions:** **Settings → Widget actions** sets the Quick settings widget's buttons (up to five: what each does, its icon and its name) and what a tap on each widget opens. Actions come from Aleph itself and from KOReader and every installed plugin that offers gesture actions, as Neo QuickSettings does. A widget can also be set to open nothing.

**Refresh distinction:** Menu/Settings → Refresh local library rescans local files. Opening Home rescans by itself only the first time in a session, ten minutes after the last scan, or when a library folder itself changed; in between, the book you close is read again on its own, so its progress is right at once. Refresh after transferring books if they do not show yet. The dashboard Quick settings refresh action instead starts or requests a quick sync from **KOSyncthing+** when available; without it, the action rescans the library.

## Languages

Aleph follows KOReader's language (KOReader's **Settings → Language**; restart KOReader after changing it). Besides English it is translated into **Brazilian Portuguese**, **Spanish**, **French** and **Italian**; Portuguese from Portugal uses the Brazilian translation, and every kind of Spanish, French or Italian uses that language's one. Where KOReader has its own translation of a word, Aleph uses KOReader's, so the two read alike. Not translated: the legal notices, and the Literary clock's quotes, which are in English.

To add a language, copy `l10n/aleph.pot` to `l10n/<code>/aleph.po`, where `<code>` is the language's folder name in KOReader's own `l10n` folder (for example `fr` or `de`), and fill in each `msgstr` line. Poedit and similar programs open these files.

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
| Kobo (OGKevin's kobo.koplugin) | On the Kobos it supports Bluetooth on, the reader menu's Bluetooth switch uses it |
| Syncery | Sync now in the reader menu; with KOSyncthing+ too, Sync runs the whole chain (Syncthing, Syncery, waiting for the other e-reader); the other e-reader's progress in the library and on book pages |
| Goodreads (advokatb, 0.5.0) | Not needed since 1.2.32: Aleph does its work itself with its code (MIT) and its files. While it is on, Aleph warns at each start and offers to turn it off, and sends nothing on its own |

The standalone **Quick Top Bar** takes precedence over Aleph's built-in top bar. Choose which implementation to use. Other plugins or patches that replace the same reader menus, highlight panels or top menu can conflict; their combinations have not all been tested.

## Network use and stored data

**X-Ray.** Finding names and mentions uses no network. Only **Describe with AI**, when you tap it, contacts the provider you chose (api.anthropic.com, api.openai.com, generativelanguage.googleapis.com, or the address you typed) with your key, the book's title and author, your progress, and short excerpts from pages already read. **Update the story** sends much more: the full text of the chapters read since the last update (up to the page you are on), in requests of about 110,000 characters. **The book before** sends that book's title and series, and its chapter summaries when it has them. The question after a break sends nothing by itself.

Ordinary library/dashboard browsing requires no server. Author portraits are off initially. When enabled, Aleph searches Open Library, then English Wikipedia, and downloads matching images from the returned image URLs. Requests include author search text and normal connection metadata. Images are cached locally; failed lookups are retried after 30 days. Bulk lookup can be stopped. Lookup requests can temporarily delay the interface on a slow connection.

**Reading bingo.** A Stats widget (sizes L, XL, M) with a card of reading challenges: **24 books** (5 × 5 with a free space in the middle) or **12 books** (4 × 3), half genre challenges, a quarter places and cultures, a quarter literary experiments, drawn from about 80 ideas and mixed so no row is all one kind. A full row or column (or, on the 5 × 5 card, a diagonal) is a bingo. Tap the widget for the full card: tap a square to choose the finished book that fills it, draw another challenge of the same kind, write your own, or empty it; **New card** starts again. When you finish a book (it closes finished, or you mark it Finished), Aleph fills its square by itself: first the square Calibre names, from a **`#bingo`** column (like tags, or text separated by commas) written into the book's file or tags like **`bingo: set in Africa`** (the square's text or part of it; these tags are not shown as genres); then a square whose challenge the book meets by its tags or genres, its format (comics), its length or its release year. When nothing fits, it asks which open square the book fills, if any (books marked Finished several at once are only placed, never asked about). A book fills one square.

**Collections from Calibre.** In Calibre, add a column with the lookup name `collections` (Preferences → Add your own columns, type "Comma separated text, like tags") and fill in each book's collections. When the books reach the device with their metadata written into the files (Polish books with "Update metadata in the book files", or sending them, which writes it), Aleph puts each book in the KOReader collections of those names, making any that are missing, and these are Aleph's collections too. Send a book again with a collection removed and it leaves that collection. Only what Aleph put there is undone: books you add to a collection on the device, and collections you make there, are left alone. It reads `metadata.opf` next to the book, the OPF inside an EPUB, or Calibre's USB device file (`metadata.calibre`); KOReader's wireless connection keeps no custom columns in its own copy, so with it only EPUBs carry the column. Each book is read once, and again only when its file changes, in the background, after a library scan and when Home opens (at most once a minute). **Settings → Library → Collections from Calibre** turns it off.

**Import from Goodreads.** On goodreads.com, My Books → Import and export → Export Library gives `goodreads_library_export.csv`. Copy it to the device (next to your books, in the Kindle's documents folder or in Downloads) and open **Settings → Library → Import from Goodreads**. Aleph shows what it would change before changing anything. For books on the device it only fills in what is empty: the status of books still unread here (Read, Currently reading, or a did-not-finish shelf), the finished date from Date Read, and a rating where there is none. When a book is Finished both here and on Goodreads but on different days, this device's day is kept unless you tap **Choose finished dates** on the summary: it lists those books with both days, and for each (or all at once) you keep this device's day or take Goodreads'. Books read on Goodreads that are not on the device go on Aleph's record of finished books, in the year they were read, so they count toward that year's goal. Read books without a Date Read are left out. Importing again does not add anything twice. Nothing is sent anywhere.

**Send to Goodreads.** A book page's **⋯** menu has **Send to Goodreads**. It sends the book's status (Finished, Reading, Unread as Want to read, On hold as Did not finish if your account has that shelf) and, for a finished book, its rating and the day it was finished. The book does not need to be open. The first time, Aleph finds it on Goodreads by the ID or ISBN in the EPUB, or offers search results to choose from, and remembers the match. A confirmation shows the Goodreads book and what will be sent before anything is sent.

**Goodreads, kept up to date.** Aleph keeps Goodreads up to date as you read, with the Goodreads code of advokatb's plugin taken into Aleph (MIT licence) and the plugin's own settings file and book links, so nothing has to be set up again. When a book opens it is linked by the Goodreads ID written in it (Calibre) or its ISBN; Goodreads then gets Currently reading, the percentage at most once a minute and when the book closes, and every status change made on the book page, on Home or in KOReader: Finished as Read with the day and your stars, On hold as Did not finish (if your account has that shelf), Unread as Want to read (only for a book Goodreads does not have). If Goodreads will not shelve a book under the Goodreads ID written in it, Aleph searches Goodreads for the same title and author and uses that book instead (crash.log says which, and what Goodreads answered). Goodreads is always asked first: a book it already has as Read only gets its stars, so it is never counted as read twice, and nothing moves a book off Read on its own. Everything is asked in a background process, so the reader never waits. Without internet, changes wait and go when Goodreads can be reached (Wi-Fi is not turned on for this); **Settings → Library → Waiting to send** shows them. **Keep Goodreads up to date**, **Track every book** (otherwise only books you track one by one from the reader menu's Goodreads button), **Send the percentage** and **Send the stars** are in Settings → Library. **If advokatb's Goodreads plugin is still installed and on**, a warning appears each time KOReader starts: Goodreads is part of Aleph now, so turn the plugin off. **Turn off** does it (as Tools → Plugin management would) and offers to restart KOReader. Until it is off, Aleph sends nothing to Goodreads on its own, so nothing is sent twice; Settings → Library offers the same button.

**Goodreads cookie.** **Settings → Library → Goodreads sign-in** (under Import from Goodreads) renews the Goodreads sign-in without pasting cookies by hand. Install the **Aleph Goodreads cookie** extension (the `aleph-goodreads-cookie` zip released next to Aleph) in Chrome, Edge or Firefox on a computer signed in to goodreads.com. Open the screen on the e-reader; it shows an address and a four-digit code. Click the extension, enter both and press Send. Aleph saves the cookies in the Goodreads settings and stops listening. The screen listens only while it is open, for at most 10 minutes, and stops after a cookie arrives or after five wrong codes. On a Kindle it opens the firewall for its port (8769) and closes it again. The cookies cross the local network unencrypted, so use it on a network you trust.

Attribution links open only when selected. Dictionary/Wikipedia/translation and third-party plugin actions retain their own network behavior. Aleph has no BookOrbit login, API synchronization or self-updater; Storefront can manage plugin updates.

Aleph stores:

- `settings/aleph_index.lua`: rebuildable library metadata, device paths and highlight excerpts.
- KOReader's `aleph` settings table: preferences, layouts, margins, pin presentation and custom highlight palette. Aleph applies that palette to KOReader's shared highlight tables while active.
- KOReader's `aleph_topbar` settings table: launcher icons, order, visibility and appearance (copied once from the Quick Top Bar plugin's `quicktopbar` table, which that plugin keeps).
- `cache/aleph/`: covers, generated art/icons, chapter maps, portraits and saved pinned images.
- KOReader book settings: user-requested rating/status changes, pins and background options. Collection and annotation actions use KOReader's own data mechanisms. Global highlight names/colors and gesture choices also modify their respective KOReader settings.

The library index is device-specific; build it separately on each device. Use Syncthing independently and refresh the local library after transfers finish. Removing an indexed folder does not delete books; history entries can still include existing books from that location. Cancelling a scan or encountering an unreadable root preserves the previous index; individual unreadable books retain a previous entry when available.

**Do not indiscriminately delete `cache/aleph/`: pinned image files live there.** A copy of every book's pins is kept in `settings/aleph_pins_backup.lua`, so a book whose settings KOReader resets offers to bring its pins back. Back up book sidecars, KOReader settings and pinned image files before reset/migration. Update by replacing the plugin folder with the new release and restarting. Disabling/removing the plugin does not automatically erase its saved preferences, gesture bindings or book-data changes.

## Troubleshooting and reports

For missing books, check folder selection and filters, then refresh. For empty time statistics, enable KOReader's Reading statistics and collect reading data. For visual conflicts, switch off the affected Aleph feature and restart if needed. Freezes when closing a book usually mean another home screen plugin, such as ZenOS or Simple UI, is running too: turn it off first. For a problem when opening a book, turn on **Settings → About → Troubleshooting log**, open the book again, and the last `Aleph: debug: reader step` line in `crash.log` names the step that did not finish; turn it off again afterwards. For freezes or KOReader closing by itself, the `Aleph: memory …` lines in `crash.log` (written when a book opens and closes, every 10 minutes while reading, and as the device sleeps and wakes) show how much memory the device had left and how much KOReader used, and when it changed. An `Aleph: redraw asked N times a second` line names code (Aleph's, KOReader's or another plugin's) that keeps KOReader redrawing nonstop. Include your device model, KOReader version, Aleph version, reproduction steps and relevant `crash.log` lines in an issue. Review logs for private file paths before sharing.

## Credits and license

[Powered by BookOrbit](https://github.com/bookorbit/bookorbit).

Copyright (C) 2025–2026 neon. Additional copyright is held by the respective BookOrbit contributors.

Licensed under the GNU Affero General Public License, version 3 only, with additional terms. This software is provided without warranty. You may redistribute and modify it under those terms.

Preserve `LICENSE`, `ADDITIONAL_TERMS.md`, `NOTICE`, `MODIFICATIONS.md`, `THIRD_PARTY_NOTICES.md`, `ZENOS_NOTICE.md` and `LICENSE-GPL-3.0.md` with the plugin. The package includes attribution for BookOrbit, ZenOS, Lucide/Feather, Bookends-related design and the Literary Clock (its code, MIT; its quotes, CC BY-NC-SA 2.5, see THIRD_PARTY_NOTICES.md). Complete Lua runtime source is included in the plugin folder; release tags identify the published version.
