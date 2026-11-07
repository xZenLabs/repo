# OrbitShelf

**Your whole BookOrbit library on KOReader's Bookshelf — including the books that aren't on your device yet.**

OrbitShelf is a KOReader plugin that connects [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) to your [BookOrbit](https://github.com/bookorbit/bookorbit) server. Browse everything on the server by Series, Authors or Genres, download a book with one tap, and keep covers and descriptions offline so the shelf looks full even on a small device with Wi-Fi off.

If this plugin is useful to you, you can [support my work on Ko-fi](https://ko-fi.com/browntigerz).


![OrbitShelf on the home shelf](images/orbitshelf-home.png)

| | |
|---|---|
| **Version** | 1.2.21 |
| **KOReader** | v2026.07 or newer |
| **Needs** | [bookshelf.koplugin](https://github.com/AndyHazz/bookshelf.koplugin) (Bookshelf 6.x recommended) and bookorbit.koplugin, signed in |
| **Optional** | SimpleUI (for the footer critter) |
| **Tested on** | Kobo Clara Colour |

---

## Features

- **BookOrbit shelves in Bookshelf.** A BookOrbit shelf source with Library, Recently added, Recently read, Series, Authors, Genres, collections, smart scopes and libraries (one shelf per BookOrbit library, optionally grouped by Series, Authors or Genres). Series, Authors and Genres open as folders. A new shelf is named after its list (Authors, Recently added, the collection …) unless you name it yourself.
- **Books not on the device show too.** Tap one to **Download** it, **Open In BookOrbit**, or read its **Book Description**. Nothing downloads until you ask.
- **Hero buttons.** Download / Open In BookOrbit for books not on the device; small Remove / Open / Sync icons for books that are. Three button sizes.
- **Offline Library.** Saves every book's cover and details (description, pages, published, language, genres), about 25 KB a book, so the full library shows with Wi-Fi off. Book files are never downloaded by it.
- **Genres.** BookOrbit's lists don't include genres, so OrbitShelf looks them up once per book in the background and keeps them.
- **Search BookOrbit.** Bookshelf's search can look in your BookOrbit library instead of the device (works offline from the saved list).
- **Return To.** Bookshelf can always open (and come back from a book) on a shelf you pick, or keep its own last-shelf behaviour.
- **Add To Collection.** Hold a book (or tap one not on the device) to add it to or remove it from your BookOrbit collections. Signs in like the BookOrbit website; the password can be saved encrypted, shared with BookOrbit Tweaks if you have it.
- **Book Description popup.** A compact window that sizes itself to the text. Tap outside or the X to close.
- **E-ink options.** A Flash menu to clear ghosting where you need it: the hero, shelf page turns, Book Description, the hold menus, the Download window and Bookshelf's shelf editor.
- **Footer critter and close button.** Your SimpleUI critter in place of the page numbers, and an optional one-tap close X.
- **Battery-friendly.** Lookups run in a background process so the screen stays responsive. They pause on sleep or Wi-Fi off, and nothing runs on a timer.
- **Tells you what broke.** Problems go to `crash.log`, including which other patch or plugin interfered.

![OrbitShelf settings](images/orbitshelf-menu.png)

## Screenshots

![Offline Library](images/orbitshelf-offline-library.png)

Offline Library keeps every book's cover and details on the device — 130 of 130 books here.

![Check For New Books](images/orbitshelf-check-new-books.png)

Check For New Books: On Wi-Fi Connect, On Refresh / Sync, Both, or Update Now Only.

![Hold menu](images/orbitshelf-hold-menu.png)

Hold a BookOrbit book for Download, Open In BookOrbit, or its Book Description.

![Book Description](images/orbitshelf-book-description.png)

The Book Description popup, sized to the text.

![Downloaded](images/orbitshelf-downloaded.png)

Downloaded — open it now or later.

![On-device book](images/orbitshelf-hero-on-device.png)

A book on the device gets small Remove, Open In BookOrbit, and Sync icons instead.

---

## Install

1. Download the latest release and unzip it.
2. Copy the `orbitshelf.koplugin` folder into KOReader's `plugins` folder:
   - **Kobo:** `.adds/koreader/plugins/`
   - **Kindle:** `koreader/plugins/`
3. Restart KOReader.
4. Open **Tools → OrbitShelf** and turn on **Use BookOrbit In Bookshelf**.

Everything is **off on a new install**, so Bookshelf looks exactly as before until you turn things on.

### Updating

Copy the new `orbitshelf.koplugin` folder over the old one and restart. Your settings are kept.

### Coming from the OrbitShelf Tweaks patch

1. Delete `patches/2-orbitshelf-tweaks.lua`, plus `patches/2-zz-orbitshelf-tweaks-diagnostics.lua` if you have it.
2. Install the plugin as above.

Your settings, genres, saved lists, offline library and covers carry over. If the old patch is still there, it runs and the plugin stays off; `crash.log` says so.

---

## Settings

All under **Tools → OrbitShelf** (or **Tools → Add-ons → OrbitShelf** if you use the Add-ons menu patch).

| Setting | What it does | Default |
|---|---|---|
| **Use BookOrbit In Bookshelf** | Adds the BookOrbit shelf source | Off |
| **Rewrite Stock Series / Authors / Genres** | Points Bookshelf's own Series, Authors, Genres, Recent and Latest chips at BookOrbit | Off |
| **Return To** | Shelf Bookshelf shows when it opens or you close a book: Bookshelf's Choice (last shelf) or one you pick | Bookshelf's Choice |
| **Add To Collection → In Book Menu** | Add To Collection when holding the hero or tapping a book not on the device | Off |
| **Add To Collection → Forget Saved BookOrbit Password** / **About** | Removes the saved password / what's saved and where | — |
| **Offline Library → Keep Library Offline** | Saves every book's cover and details on the device | Off |
| **Offline Library → Check For New Books** | On Wi-Fi Connect, On Refresh / Sync, Both, or Update Now Only | On Wi-Fi Connect |
| **Offline Library → Update Now** | Pulls the list fresh and saves anything new | — |
| **Offline Library → Delete Offline Library…** | Removes saved details and trims covers | — |
| **Hero → Download / Remove Buttons** | Buttons on the hero for BookOrbit books | Off |
| **Hero → Sync Button** | Refreshes the lists and runs BookOrbit's sync | Off |
| **Hero → Button Size** | Small, Medium or Large | Small |
| **Shelf → Search BookOrbit** | Bookshelf's search looks in BookOrbit instead of the device | Off |
| **Shelf → Build / Rebuild Genres** | Looks up genres in the background | — |
| **Flash → Hero When It Changes** / **Hero: Every Change** | Clears ghosting when the hero shows another book; every change or every 4th / 6th | Off |
| **Flash → Shelf Page Turns** | Full refresh on every shelf page | Off |
| **Flash → Book Description / Hold Menu / Download Window / Bookshelf's Book Menu / Shelf Editor** | That popup's box flashes when it opens and closes | Off |
| **Footer → Footer Critter** | SimpleUI critter in place of the page numbers | Off |
| **Footer → Critter Says** | Page, Witty, Picks, Sayings | All on |
| **Footer → Close Only** / **Close Control** | One-tap close X; left, right or Bookshelf's side | Off |
| **Clean Up Cache…** | Removes old covers and saved lists | — |
| **Diagnostics** | Detailed log for 30 minutes after each start, off by itself after 3 days | Off |

### How Offline Library works

- **Start** asks first, showing the number of books and a rough size and time.
- It works two batches at a time in the background, and the shelf fills in as it goes.
- **Wi-Fi off or sleep** pauses it. It carries on when Wi-Fi is back.
- After the first run, only new or changed books are looked up. **Check For New Books** sets when that happens.
- **Turning it off** asks whether to keep or delete what's saved.

---

## Troubleshooting

OrbitShelf writes to KOReader's `crash.log` (`.adds/koreader/crash.log` on Kobo). Its lines are tagged `orbitshelf <version>:`.

**Every start:** the KOReader version, the device, the Bookshelf / BookOrbit / SimpleUI versions, and the patches and plugins installed.

**Only when something's wrong**, once per start each:
- A part that failed, with where. Bookshelf's own version runs instead, so the screen doesn't break.
- Another patch or plugin that changed a Bookshelf function OrbitShelf uses, or replaced the BookOrbit shelf source, named by file. For example:
  ```
  orbitshelf 1.2.21: Bookshelf.onHold (hero hold menu) was changed after OrbitShelf by plugins/other.koplugin/main.lua
  ```

**For more detail**, turn on **Diagnostics**, reproduce the problem within 30 minutes, then share `crash.log`. Diagnostics lines are tagged `orbitshelf <version> diag:`.

**Common issues**

| Problem | Try |
|---|---|
| No BookOrbit shelf | Check that Bookshelf and BookOrbit are installed, BookOrbit is signed in, and **Use BookOrbit In Bookshelf** is on. `crash.log` will say which one is missing. |
| Genres shelf empty | Open it once and tap **Start**, or use **Shelf → Build Genres** with Wi-Fi on. |
| Closing the shelf shows the file browser | That's Bookshelf's **Instant book close (beta)**, not OrbitShelf. Turn it off in Bookshelf's settings. |
| Ghosting on the hero, shelf or a popup | Turn on what you need under **Flash**. |

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
├── orbitshelf_footer.lua      footer critter, close X
├── orbitshelf_collections.lua Add To Collection (website sign-in, saved password)
├── orbitshelf_menu.lua        settings menu
├── orbitshelf_diag.lua        Diagnostics (loaded only while it's on)
└── README.md
```

**What it stores on the device**
- Settings and genres live in KOReader's settings.
- Saved lists are in `koreader/orbitshelf-lists.lua`.
- Offline details are in `koreader/orbitshelf-library.txt`.
- Covers are in `koreader/cache/bookorbit/`, shared with BookOrbit.

---

## Changelog

The full history is at the top of `main.lua`.

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
