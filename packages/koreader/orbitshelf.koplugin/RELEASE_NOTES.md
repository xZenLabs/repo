# v2.0.2 · 2026-11-17

## 2.0.2 (2026-11-17)

- **Add To Collection uses a BookOrbit API key** (needs BookOrbit 3.8.0+ on the server) instead of the website password.
  - Create a key under Settings > You > API keys with **Read and write**.
  - Easiest: OrbitShelf → BookOrbit Sign-In → **Create API Key File** (writes `koreader/orbitshelf_api_key.txt`), paste the key on the marked line over USB, then Add To Collection or Set API Key… — imported, encrypted (AES-256), temp file deleted.
  - Or: Set API Key… on device.
  - Menu shows **BookOrbit Sign-In · API key active** / **API Key Active** when a key is saved.
  - Forget Saved API Key clears it (shared with BookOrbit Tweaks).
  - Shared with BookOrbit Tweaks 2.17.0+: same encrypted key and temp file.
  - About The API Key opens a scrollable window.
- **Downloads › Book Type** — how a read-along EPUB (with narration) downloads:
  - **Text Only** (default) — without narration, as before
  - **With Narration** — the book with its audio (for apps that play EPUB narration). If the book has no narration file: **No narration file for this book.** (nothing is downloaded)
  - **Both** — text-only copy plus "… - With Narration" beside it; remove takes both. The done note lists what arrived and what didn't (text / narration none / narration failed)
  - **Same As BookOrbit** — follow the server's EPUB delivery setting for this device

# v2.0.1 · 2026-11-15

2.0.0 was never released on its own, so this release carries both 2.0.0 and 2.0.1.

## 2.0.1
- A reading status set with Wi-Fi off can be dropped before it's sent: Reading Status… starts with Don't Send <status> while one is waiting, and the covers go back to the status the book had. The hero's button says Status · Queued meanwhile.
- The BookOrbit · Queue shelf shows books waiting to download only.
- Clean-up: an unused return value removed.

## 2.0.0 — OrbitShelf 2.0 ("your library, ready offline")
- Book Page: hold a book, or Book Page in its menu — cover with status, title, author, series, status, progress and last read, pages / year / language / genres; buttons beside the cover (full-width under it on a tall book); Bulk Download, Bulk Remove and Help in the top bar with where the book is and the free space; the description; the series, more by the author, or similar books with status and On device / Queued on each cover. The page opens on the series (or More by); Similar › or a swipe left past it shows Similar books, ‹ or a swipe right goes back. Also in Bookshelf's book menu (and the file browser's) for a BookOrbit book on the device. Opens over Bookshelf, closes on sleep and when a book opens; BookOrbit opened from it comes back to it.
- The Queue: with Wi-Fi off, downloads and reading statuses wait; the queue runs once 15 s after Wi-Fi connects (statuses first, books one at a time, 50 MB kept free) or Download Queue Now. A sent status sticks after a refresh. Clock mark on queued covers; BookOrbit · Queue shelf. No timers, no polling; sleep pauses it.
- Up Next shelf: the next book in every series you've started.
- Covers show BookOrbit's reading status and progress (Bookshelf's own badges) for books not on the device.
- Remove Finished Books (Downloads, Not Opened For) and a Finished Books select in Bulk Remove. Bulk Remove on every Book Page.
- Hero: Status button for a quick Reading Status; Remove Queue on a queued book.
- Settings regrouped: Shelves, Books, Downloads, Look, Offline, Footer, Advanced, Help. Always on: Add To Collection, Reading Status, Bulk Download / Remove (under More… in a book's menu). Single choices for Flash, Hero Buttons, Close X, Home Button, Next Book In Series (Off / Ask / Add To Queue), read from the 1.x settings: nothing you set is changed, and 1.2.x still loads them.
- Help at the bottom of Tools › OrbitShelf (Getting Started … What's New, newest version first), each topic in a window sized to it; What's New pops up once after the update.
- Bigger footer critter.
- Waking to Simple UI's home (its Start With Home Screen) with Bookshelf left open closes Bookshelf under the home, so it no longer pops up by itself when Wi-Fi connects.
- Fix: paging a series strip past the book shown jumped back to the books around it, so a long series' later books never showed.
- Clean-up: the start-up environment lines (versions, patches, plugins) only with Diagnostics on; unused code removed.

# v1.2.26 · 2026-11-11

Spines need Bookshelf 6.4 (or its feat-588 test branch) — until 6.4 lands for everyone, Spines stay off on stock Bookshelf.

1.2.26
- Shelf > Mark Style for the Not On Device mark: Auto (the default) draws it black on a light cover corner and white on a dark one, with a thin outline in the other colour so it reads on a busy corner too; Badge puts it on a small round disc in Bookshelf's badge colours, like its page-count pill. Night mode keeps the contrast either way.

1.2.25
- Shelf > Mark Books Not On Device (off by default): BookOrbit's download mark on the bottom-left of a BookOrbit cover whose book isn't on the device; books on the device stay as they are. Covers view only.
- Footer > Home Button (off by default): a house in the footer corner opposite the close X / hamburger, back to page 1. Home Goes To: This Shelf or a shelf you pick.

# v1.2.24 · 2026-11-10

1.2.24 — Extras menu: Bulk Download, Bulk Remove, Reading Status, Next In Series. Shelf filter (On Device / Not On Device). Download progress %.

Bulk Download / Remove: hold a book, tap Bulk Download… or Bulk Remove…, tick books from that shelf (All, Same Series, Same Author or None). Downloads check size and free space first, then go one at a time. Off by default.
Reading Status: set a book's BookOrbit status (Read, Reading, Want To Read …) from its hold menu. Off by default.
Next In Series: finish a book and, back on the home screen, get asked whether to download the next one in the series. Off by default.
Show On Device / Not On Device: a shelf can show only the books on the device, or only the ones that aren't.
Download progress: big downloads show their % in the corner.

Note: Spines (Series / Authors / Genres shelves as runs of book spines) needs Bookshelf 6.4 — on older Bookshelf everything works as before, the option just isn't there.

# v1.2.23 · 2026-11-07

OrbitShelf 1.2.23 — Spines for BookOrbit shelves: Series, Authors and Genres (and Group By shelves) stand as runs of their books' spines under each group's name, like Bookshelf's own Series shelf. Covers view is unchanged: groups are still folders there.

Note: Spines is for the Spines view when Bookshelf 6.4 drops — it needs Bookshelf 6.4 (or its feat-588 test branch). On older Bookshelf, everything works as before; the Spines option simply isn't there yet.
