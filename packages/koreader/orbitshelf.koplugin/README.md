# OrbitShelf

**Your whole BookOrbit library on KOReader's Bookshelf — including the books that aren't on your device yet.**

OrbitShelf is a KOReader plugin that connects [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) to your [BookOrbit](https://github.com/bookorbit/bookorbit) server. Browse everything on the server by Series, Authors or Genres, download a book with one tap, and keep covers and descriptions offline so the shelf looks full even on a small device with Wi-Fi off.

If this plugin is useful to you, you can [support my work on Ko-fi](https://ko-fi.com/browntigerz).


![OrbitShelf on the home shelf](images/orbitshelf-home.png)

| | |
|---|---|
| **Version** | 2.2.0 |
| **KOReader** | v2026.07 or newer |
| **Needs** | [bookshelf.koplugin](https://github.com/AndyHazz/bookshelf.koplugin) (Bookshelf 6.x recommended) and bookorbit.koplugin, signed in |
| **Optional** | SimpleUI (footer critter, the stats critters), X-Ray or KOAssistant, Glimpse, ReadMastery, ShelfSync (each adds to the Book Page and Reading Stats when installed) |
| **Tested on** | Kobo Clara Colour |

---

## Features

- **Reading Stats** (new in 2.2). **Book | Stats | All Time** at the top of the Book Page. **Stats**: one book in tiles: time, days, pace, when you'll likely finish, this week, Day by Day (a ring of the whole read), the calendar, chapters, habits and **Moments**, with highlights, bookmarks, X-Ray and Glimpse a tap away. **All Time**: all your reading (time, days, books, the months ring, authors, genres, habits) and **Your Year** (a ring of the year and the year's shelf of spines: tap one for that book). From your KOReader statistics or from BookOrbit's reading sessions (every device, listening too). ReadMastery's rewards, X-Ray (or KOAssistant's) and Glimpse's pictures show up too, spoiler-free. What you've seen once works offline, and **Save All Stats For Offline** saves the lot.
- **Settings window** (new in 2.2). Groups on the left, their settings on the right, open until ✕. **Help › Quick Setup** puts the main choices in one popup (shown once after install or update).
- **Look** (new in 2.2). **Colour** on or off (off: everything plain), **Colour Theme** (Vibrant, Pastel, Ocean, Sunset, Forest, Kobo Mono or your own), **Popup Style** (Standard, Rainbow, or Solid in a colour you pick) and **Screen Flashes** for each kind of screen.
- **BookOrbit shelves in Bookshelf.** A BookOrbit shelf source with Library, Recently added, Recently read, Series, Authors, Genres, collections, smart scopes and libraries (one shelf per BookOrbit library, optionally grouped by Series, Authors or Genres). Series, Authors and Genres open as folders. With Bookshelf 6.4 (or its feat-588 test branch) they can be shown as **Spines** too: each series, author or genre stands as a run of its books' spines under its name, covers colour the spines and page counts set their thickness, best with Offline Library on. A new shelf is named after its list (Authors, Recently added, the collection …) unless you name it yourself.
- **Books not on the device show too.** Tap one to **Download** it, **Open In BookOrbit**, or read its **Book Description**. Nothing downloads until you ask.
- **Hero buttons.** Download / Open In BookOrbit for books not on the device; small Remove / Open / Sync icons for books that are. Three button sizes.
- **Offline Library.** Saves every book's cover and details (description, pages, published, language, genres), about 25 KB a book, so the full library shows with Wi-Fi off. Book files are never downloaded by it.
- **Genres.** BookOrbit's lists don't include genres, so OrbitShelf looks them up once per book in the background and keeps them.
- **Search BookOrbit.** Bookshelf's search can look in your BookOrbit library instead of the device (works offline from the saved list).
- **Return To.** Bookshelf can always open (and come back from a book) on a shelf you pick, or keep its own last-shelf behaviour.
- **Add To Collection.** Hold a book (or tap one not on the device) to add it to or remove it from your BookOrbit collections. Signs in like the BookOrbit website; the password can be saved encrypted, shared with BookOrbit Tweaks if you have it.
- **Bulk Download / Remove.** Hold a book, tap **Bulk Download…** or **Bulk Remove…**, tick books from that shelf (All, Same Series, Same Author, Finished Books or None). Downloads check size and free space first, then go one at a time.
- **Remove Finished Books.** **Downloads → Remove Finished Books…** removes the finished BookOrbit books you haven't opened here for a while (**Not Opened For**: 7, 30 or 90 days, or any). It always asks first, and the books stay in BookOrbit.
- **Reading Status.** Set a book's BookOrbit status (Read, Reading, Want To Read …) from its hold menu, the Book Page, or the hero's **Status** button.
- **Book Page.** Everything about a book on one page. Hold a book that isn't on the device (with **Hold A Book Opens: Book Page**), tap **Book Page** in its quick menu, or, for a BookOrbit book on the device, tap the **Book Page** card in Bookshelf's book menu. The cover shows its status (Read, On Hold 30% …) and On device / Queued; beside it the title (tap for all of it), author, series, status, progress and when it was last read (this Kobo's history or BookOrbit's), a finished date for a book finished here, pages / year / language / genres, and the buttons: Download / Open, Reading Status / Collection, BookOrbit / Remove. The top bar has Bulk Download, Bulk Remove and Help, with where the book is and the free space. Then the description (tap to read it all) and, at the bottom, the series in order (5 at a time, swipe or the arrows for more) or more by the author. **Similar ›** (or a swipe left past them) switches to Similar books (BookOrbit's own picks, else by genre); **‹ Series** or a swipe right goes back. It works offline from what's saved, closes on sleep and when a book opens, and BookOrbit opened from it comes back to it.
- **The Queue.** With Wi-Fi off, the hero's **Download** becomes **Queue** (and the Not On Device menu has **Add To Queue**); **Reading Status…** saves the status to send later, and the cover changes now. It runs by itself 15 seconds after Wi-Fi connects, or with **Download Queue Now**: statuses first, then the books one at a time, each checked for free space. Sleep or Wi-Fi off stops it and the next connect carries on. No timers, and it never turns Wi-Fi on. Queued covers show a small clock, and the hero's button turns into **Remove Queue**. A waiting status can be dropped before it's sent: while one waits, the hero's button says **Status · Queued** and **Reading Status…** starts with **Don't Send**, and the covers go back to what the book had. **Tools → OrbitShelf → Downloads** lists it all (Move To Top, Remove, Clear Queue…) with free space; add a **BookOrbit · Queue** shelf in Bookshelf to see the books waiting to download.
- **Status on covers.** Books not on the device show BookOrbit's reading status and progress with Bookshelf's own cover badges (progress bar, reading bookmark, done tick). On the device, KOReader's own status shows as always. Bookshelf's badge settings decide what's drawn.
- **Up Next shelf.** **BookOrbit · Up Next**: for every series you've started, the next book after the furthest one you've read or are reading.
- **Next In Series.** Finish a book and, back on the home screen, get asked whether to download the next one in the series (or have it added to the Queue). Off by default.
- **Show On Device / Not On Device.** A shelf can show only the books on the device, or only the ones that aren't.
- **Mark Books Not On Device.** BookOrbit's download mark (the one the Side Panel uses) on the bottom-left of covers whose book isn't on the device, so you can see at a glance what's left to download. Books on the device stay clean; the page count keeps the bottom-right. Mark Style: black or white depending on the cover (Auto), or on a small round badge. Off by default.
- **Download progress.** Big downloads show their % in the corner.
- **Book Description popup.** A compact window that sizes itself to the text. Tap outside or the X to close.
- **E-ink options.** A Flash menu to clear ghosting where you need it: the hero, shelf page turns, Book Description, the hold menus, the Download window and Bookshelf's shelf editor.
- **Footer critter, close and Home buttons.** Your SimpleUI critter in place of the page numbers, an optional one-tap close X, and an optional Home button in the other corner that jumps back to page 1 (of this shelf, or of a shelf you pick).
- **Battery-friendly.** Lookups run in a background process so the screen stays responsive. They pause on sleep or Wi-Fi off, and nothing runs on a timer.
- **Help built in.** **Tools → OrbitShelf → Help**: Getting Started, Shelves, Book Page, Downloads And The Queue, Offline Library, Look / Footer / Flashing, Something's Wrong and What's New, each in a small window. What's New also pops up once after an update.
- **Plays well with Simple UI.** Waking to Simple UI's home with Bookshelf left open closes Bookshelf under it, so Bookshelf doesn't pop up by itself when Wi-Fi connects.
- **Tells you what broke.** Problems go to `crash.log`, including which other patch or plugin interfered.

![OrbitShelf settings](images/orbitshelf-menu.png)

## Screenshots

![Offline Library](images/orbitshelf-offline-library.png)

Offline Library keeps every book's cover and details on the device — 130 of 130 books here.

![Check For New Books](images/orbitshelf-check-new-books.png)

Check For New Books: On Wi-Fi Connect, On Refresh / Sync, Both, or Off (Update Now only).

![Hold menu](images/orbitshelf-hold-menu.png)

Hold a BookOrbit book for Download, Open In BookOrbit, or its Book Description.

![Book Description](images/orbitshelf-book-description.png)

The Book Description popup, sized to the text.

![Downloaded](images/orbitshelf-downloaded.png)

Downloaded — open it now or later.

![On-device book](images/orbitshelf-hero-on-device.png)

A book on the device gets small Remove, Open In BookOrbit, and Sync icons instead.

![Book Page — Series](images/orbitshelf-book-page-series.png)

The Book Page: cover, status, progress and description, with the series below — Codex Alera, 0 of 6 read. Swipe left past it for Similar books.

![Book Page — Similar books](images/orbitshelf-book-page-similar.png)

Similar books on the Book Page — BookOrbit's picks, or by genre when it has none. Each cover shows its status and On device / Queued.

![Book Page — Download](images/orbitshelf-book-page-download.png)

The Book Page for a book not on the device: Download, Reading Status, Collection, BookOrbit. With Wi-Fi off the button reads Queue and the download waits.

![Up Next](images/orbitshelf-up-next.png)

Up Next: the next book in every series you've started — Academ's Fury (#2) and The Wicked King (#2) here.

![Queue](images/orbitshelf-queue.png)

The Queue shelf: books waiting to download, clock-marked, with their place in the series.

---

## Install

1. Download the latest release and unzip it.
2. Copy the `orbitshelf.koplugin` folder into KOReader's `plugins` folder:
   - **Kobo:** `.adds/koreader/plugins/`
   - **Kindle:** `koreader/plugins/`
3. Restart KOReader.
4. Open **Tools → OrbitShelf** and turn on **Use BookOrbit In Bookshelf** (Shelves).

Everything is **off on a new install** (Reading Stats aside), so Bookshelf looks exactly as before until you turn things on. The first time a BookOrbit shelf shows, **Quick Setup** offers the main choices.

### Updating

Copy the new `orbitshelf.koplugin` folder over the old one and restart. Your settings are kept. After updating to 2.2, Quick Setup shows once with what you have now; nothing changes unless you pick it.

### Coming from the OrbitShelf Tweaks patch

1. Delete `patches/2-orbitshelf-tweaks.lua`, plus `patches/2-zz-orbitshelf-tweaks-diagnostics.lua` if you have it.
2. Install the plugin as above.

Your settings, genres, saved lists, offline library and covers carry over. If the old patch is still there, it runs and the plugin stays off; `crash.log` says so.

---

## Settings

**Tools → OrbitShelf** (or **Tools → Add-ons → OrbitShelf** with the Add-ons menu patch), or **More ▾ › Settings** on the Book Page, opens the Settings window: the groups on the left, the picked group's settings on the right. A switch with a › has settings of its own: tap the switch to turn it on or off, tap its words for its settings. Hold any setting for what it does.

| Setting | What it does | Default |
|---|---|---|
| **BookOrbit Account** | About The API Key, Create API Key File, Set API Key…, Forget Saved API Key; **Save All Stats For Offline** (every book you've read in BookOrbit and your years, saved now; Wi-Fi on) | — |
| **Books → Book Page: Reading Stats** | Book \| Stats \| All Time on the Book Page | On (new installs) |
| **Books → Hold A Book Opens** | Holding a book not on the device: Quick Menu or Book Page | Quick Menu |
| **Books → Next Book In Series** | Finishing a book: Off, Ask (back home) or Add To Queue | Off |
| **Downloads → Book Type** | Read-along books: Text Only, With Narration, Both, or Same As BookOrbit | Text Only |
| **Downloads → Queue** | What's waiting for Wi-Fi, Download Queue Now, Clear Queue… | Empty |
| **Downloads → Remove Finished Books** | Not Opened For (any, 7, 30, 90 days) and Remove Now… (asks first) | 30 days |
| **Footer → Footer Critter** | SimpleUI critter in place of the page numbers; its settings: what it says (Page, Witty, Picks, Sayings) | Off |
| **Footer → Close X** | Off, Left, Right or Bookshelf's Side: the hamburger becomes a one-tap close X | Bookshelf's Side |
| **Footer → Home Button** | Off, This Shelf or a shelf you pick: back to page 1 | Off |
| **Look → Cover Marks** | Download mark on covers not on the device (queued books show a clock); its settings: Mark Style | Off |
| **Look → Hero Buttons** | Download / Queue and Open In BookOrbit on the hero; Remove, Open and Sync icons for books on the device; its settings: size | Off |
| **Look → Colour** | Buttons, popup sections, the Book Page's boxes and Settings in colour; off, everything plain (charts keep their colours) | Off |
| **Look → Colour Theme** | Vibrant, Pastel, Ocean, Sunset, Forest, Kobo Mono or Custom | Vibrant |
| **Look → Popup Style** | The popups' edge: Standard, Rainbow or Solid (Solid Colour: one of 8) | Standard |
| **Look → Screen Flashes** | Book Page, Book Page Changes, Hero, Popups, Shelf Pages, Stats Page, Stats Page Changes: No, Quick or Full Flash | as before |
| **Offline → Keep Library Offline** | Saves every book's cover and details; its settings: Check For New Books, Update Now, Delete | Off |
| **Offline → Build / Rebuild Genres** | Looks up genres in the background | — |
| **Shelves → Use BookOrbit In Bookshelf** | Adds the BookOrbit shelf source | Off |
| **Shelves → Rewrite Stock Series / Authors / Genres** | Points Bookshelf's own chips at BookOrbit | Off |
| **Shelves → Search BookOrbit** | Bookshelf's search looks in BookOrbit | Off |
| **Shelves → Return To** | Bookshelf's Choice (last shelf) or a shelf you pick | Bookshelf's Choice |
| **Advanced → Diagnostics** | Detailed log in crash.log for 30 minutes after each start, off by itself after 3 days | Off |
| **Advanced → Clean Up Cache…** | Removes old covers and saved lists | — |
| **Help** | Quick Setup, then how OrbitShelf works one topic at a time, and What's New | — |
| **Shelf editor → Show** / **BookOrbit · Queue** | All Books, On Device or Not On Device / a shelf of the books waiting to download | All Books |

### How Offline Library works

- **Start** asks first, showing the number of books and a rough size and time.
- It works two batches at a time in the background, and the shelf fills in as it goes.
- **Wi-Fi off or sleep** pauses it. It carries on when Wi-Fi is back.
- After the first run, only new or changed books are looked up. **Check For New Books** sets when that happens.
- **Turning it off** asks whether to keep or delete what's saved.

---

## Troubleshooting

OrbitShelf writes to KOReader's `crash.log` (`.adds/koreader/crash.log` on Kobo). Its lines are tagged `orbitshelf <version>:`.

**When something's wrong**, once per start each:
- A part that failed, with where. Bookshelf's own version runs instead, so the screen doesn't break.
- Another patch or plugin that changed a Bookshelf function OrbitShelf uses, or replaced the BookOrbit shelf source, named by file. For example:
  ```
  orbitshelf 1.2.23: Bookshelf.onHold (hero hold menu) was changed after OrbitShelf by plugins/other.koplugin/main.lua
  ```

**For more detail**, turn on **Diagnostics**, reproduce the problem within 30 minutes, then share `crash.log`. Diagnostics lines are tagged `orbitshelf <version> diag:`; with it on, each start also writes the KOReader version, the device, the Bookshelf / BookOrbit / SimpleUI versions, and the patches and plugins installed.

**Common issues**

| Problem | Try |
|---|---|
| No BookOrbit shelf | Check that Bookshelf and BookOrbit are installed, BookOrbit is signed in, and **Use BookOrbit In Bookshelf** is on. `crash.log` will say which one is missing. |
| Genres shelf empty | Open it once and tap **Start**, or use **Offline → Build Genres** with Wi-Fi on. |
| Closing the shelf shows the file browser | That's Bookshelf's **Close books in the background** (called **Instant book close (beta)** before Bookshelf 6.5), not OrbitShelf. Turn it off in Bookshelf's settings. |
| Ghosting on the hero, shelf or a popup | Pick a flash for it under **Look → Screen Flashes**. |
| No stats for a book | Turn on **Books → Book Page: Reading Stats**. A book never read on this Kobo shows BookOrbit's stats (needs the API key, and Wi-Fi the first time). |

---

## Files

```
orbitshelf.koplugin/
├── _meta.lua                  plugin info and version
├── main.lua                   start-up, menu, Wi-Fi and sleep events, changelog
├── orbitshelf_core.lua        settings, crash.log reporting, conflict checks
├── orbitshelf_bookorbit.lua   BookOrbit lists, covers, offline details, download / remove, Book Description
├── orbitshelf_genres.lua      background lookups (Genres, Offline Library)
├── orbitshelf_source.lua      the Bookshelf source and its shelves
├── orbitshelf_hero.lua        hero buttons, status line, flash
├── orbitshelf_footer.lua      footer critter, close X, Home button
├── orbitshelf_collections.lua Add To Collection (website sign-in, saved password)
├── orbitshelf_bulk.lua        Bulk Download / Remove (checklist, size check, download queue)
├── orbitshelf_extras.lua      Reading Status, Next In Series, Not On Device mark
├── orbitshelf_queue.lua       the Queue (downloads and statuses waiting for Wi-Fi)
├── orbitshelf_bookpage.lua    the Book Page
├── orbitshelf_menu.lua        settings (their rows), Help, Quick Setup, What's New
├── orbitshelf_settings.lua    the Settings window
├── orbitshelf_sheet.lua       the popups (sheets), Popup Style, Colour
├── orbitshelf_theme.lua       Colour Theme
├── orbitshelf_bookmore.lua    the Book Page's More ▾, highlights, bookmarks
├── orbitshelf_stats.lua       Reading Stats (one book; This Kobo / BookOrbit)
├── orbitshelf_alltime.lua     All Time
├── orbitshelf_rings.lua       Day by Day, Your Year and their rings and shelf
├── orbitshelf_xray.lua        X-Ray / KOAssistant and ReadMastery for the stats
├── orbitshelf_glimpse.lua     Glimpse's pictures for the stats
├── orbitshelf_diag.lua        Diagnostics (loaded only while it's on)
└── README.md
```

**What it stores on the device**
- Settings and genres live in KOReader's settings.
- Saved lists are in `koreader/orbitshelf-lists.lua`.
- Offline details are in `koreader/orbitshelf-library.txt`.
- Covers are in `koreader/cache/bookorbit/`, shared with BookOrbit.
- Reading Stats' saved numbers (per book, your years, BookOrbit's sessions) are in `koreader/cache/bookorbit/orbitshelf_stats.lua`; ReadMastery notes and X-Ray look-ups per book in `koreader/settings/orbitshelf_reading_log.lua`.

---

## Changelog

The full history is in [CHANGELOG.md](CHANGELOG.md).

- **2.2.0:** Reading Stats (Book | Stats | All Time, Your Year, Moments with ReadMastery, X-Ray / KOAssistant and Glimpse, This Kobo or BookOrbit, saved for offline), the Book Page redesigned with More ▾, a Settings window with Quick Setup, and Look's Colour, Colour Theme, Popup Style and Screen Flashes. Look's choices now kept after a restart; the API key shared with BookOrbit Tweaks opens in OrbitShelf.
- **2.0.2:** Add To Collection uses a BookOrbit API key (server 3.8.0+, Read and write) instead of the website password — shared with BookOrbit Tweaks 2.17.0, same encrypted store; Create API Key File in BookOrbit Sign-In. Downloads › Book Type: Text Only / With Narration / Both / Same As BookOrbit for read-along EPUBs.
- **2.0.1:** A reading status set with Wi-Fi off can be dropped before it's sent (**Don't Send** in Reading Status…, the hero says **Status · Queued** meanwhile), and the covers go back. The **BookOrbit · Queue** shelf shows only books waiting to download, so **Remove Queue** takes a book off it at once.
- **2.0.0:** OrbitShelf 2.0 ("your library, ready offline"), tested as 1.3.11–1.3.24 and 2.0.1–2.0.4. The Book Page grown up: buttons beside the cover, last read and finished dates, Bulk Download / Remove and Help in its top bar, statuses on every cover, Similar books one swipe or tap from the series or More by, a Book Page card in Bookshelf's book menu for books on the device, and BookOrbit opened from it coming back to it. A sent reading status sticks after a refresh. Up Next shelf. Remove Finished Books and a Finished Books select in Bulk Remove. Hero Status button. Help menu with What's New. Bigger footer critter. Bookshelf no longer pops up after waking to Simple UI's home. Fix: a long series' later books never showed in the strip. Start-up environment lines only with Diagnostics on; unused code removed. Nothing you set is changed by the update.
- **1.3.10:** Fix: the Book Page closes on sleep, so it isn't left open (and glitched) behind the home screen after waking.
- **1.3.9:** Book Page: More by / Similar books show each book's BookOrbit status (Read, On Hold…), so a finished book doesn't look new; the series strip uses the same words. Check For New Books off choice reads "Off (Update Now only)".
- **1.3.8:** Settings regrouped (Shelves, Books, Downloads, Look, Offline, Footer, Advanced); Add To Collection, Reading Status and Bulk Download / Remove always there (More… in a book's menu); Flash, Hero Buttons, Close X, Home Button and Next Book In Series (now with Add To Queue) are single choices set from what you had; a one-time note says so. Book Page: Similar books for a book with no series and nothing else by its author.
- **1.3.7:** Book Page: no white outlines around covers in night mode; tap the description to read all of it.
- **1.3.6:** Book Page flashes only when it opens and closes.
- **1.3.5:** Book Page: plain strip covers, status in words under series books, the description fills the space.
- **1.3.4:** Book Page: Help in More, Remove's question on top, Bulk windows return to the page, more by the author when there's no series.
- **1.3.3:** The Book Page (Hold A Book Opens: Book Page, or the quick menu's Book Page row). Hero says Remove Queue.
- **1.3.2:** A queued book's hero button says Remove From Queue.
- **1.3.1:** The Queue: with Wi-Fi off, Download and Reading Status wait in a queue that runs a little after Wi-Fi connects (statuses, then books one at a time, space checked). Clock on queued covers, Queue menu and BookOrbit · Queue shelf.
- **1.3.0:** Covers of books not on the device show BookOrbit's reading status and progress with Bookshelf's own badges (KOReader's own status still wins on the device). Fills in on each list's next refresh.
- **1.2.26:** Mark Style for the Not On Device mark: Auto Black / White or Badge.
- **1.2.25:** Mark Books Not On Device (download mark on covers not on the device). Footer Home button (page 1 of this shelf or a shelf you pick).
- **1.2.24:** Extras menu: Bulk Download, Bulk Remove, Reading Status, Next In Series. Shelf filter (On Device / Not On Device). Download progress %.
- **1.2.23:** On Spines, Series / Authors / Genres show each group as a run of spines.
- **1.2.22:** Spines for BookOrbit shelves (Bookshelf 6.4 or its feat-588 test branch).
- **1.2.21:** Footer critter gets SimpleUI 3.0.3's ground shadow.
- **1.2.20:** Lookups two at a time: same speed, less battery.
- **1.2.19:** New BookOrbit shelves are named after their list; popup flashes cover only the popup.
- **1.2.18:** BookOrbit shelf ready at start-up without waiting on Bookshelf; sturdier background results.
- **1.2.17:** New covers download in the background (no freeze); saved lists in their own file; lighter background checks.
- **1.2.16:** Flash menu: every flash option in one place, plus flash for Book Description, the hold menus, the Download window and Bookshelf's shelf editor.
- **1.2.15:** No blank bar left on the shelf after signing in for Add To Collection.
- **1.2.13:** Return To in the menu; menu reordered; hero button text centred and no longer cut short.
- **1.2.12:** Add To Collection.
- **1.2.11:** Hero pills and status line match the hero's font and line up in list view.
- **1.2.10:** Hero flash every 4th / 6th change; old lists show at once and refresh in the background.
- **1.2.9:** Corner notes fit on one line; Diagnostics time taps on books.
- **1.2.8:** Group By for Library, Collection and Smart Scope shelves.
- **1.2.7:** Library shelves (one shelf per BookOrbit library).
- **1.2.6:** Smart Scope shelves; Search BookOrbit; downloads run in the background with a corner note.
- **1.2.5:** Reports show BookOrbit's version; Diagnostics lists every setting.
- **1.2.4:** Check For New Books option. README.
- **1.2.3:** Fixed a crash when scrolling a long description, and the screen freezing during lookups.
- **1.2.2:** Lookups three at a time; fewer shelf redraws.
- **1.2.1:** Hero Button Size.
- **1.2.0:** Book Description popup.
- **1.1.x:** Diagnostics built into the plugin, written to crash.log.
- **1.0.x:** OrbitShelf Tweaks 1.6.1 as a plugin. Everything off by default, with problems reported in crash.log.

---

## Credits

- [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) by AndyHazz: the shelf OrbitShelf plugs into.
- [BookOrbit](https://github.com/bookorbit/bookorbit) and its KOReader plugin: the server and API.
- [KOReader](https://github.com/koreader/koreader).
