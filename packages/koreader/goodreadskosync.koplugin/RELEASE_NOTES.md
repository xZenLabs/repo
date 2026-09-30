# v1.18.1


"Browse Goodreads" now renders pages properly instead of showing plain text.

- Pages open in KOReader's HTML engine, so headings, paragraphs, lists and links are formatted.
- Tapping a link shows an **Open in Goodreads reader** option, so you keep browsing in place.
- A small top bar offers **Back / Reload / Home**.
- JavaScript-only screens and forms are still not rendered (writes use the plugin's own actions).

# v1.18.0


Adds a built-in Goodreads reader, so you can browse Goodreads on the device.

- New **Browse Goodreads…** in the main menu: reads pages with your existing sign-in and shows them as clean text, with the page's links listed so you can keep browsing.
- Navigation: Back / Forward / Reload / Home / Open URL / Close.
- Covers the server-rendered parts of Goodreads (home, My Books, book pages, reviews, notes, profile, quotes, recommendations…). JavaScript-only screens and forms are not rendered — writing to Goodreads still happens through the plugin's own actions.
- Nothing is sent anywhere except goodreads.com.

# v1.17.4


Every change is now saved on the device first and posted in the background, and the last long network burst is gone.

- Ratings, shelf changes, and the reading goal are queued locally first and sync in the background — the same way notes already did.
- "Sync now" with no book open pushes linked books in small batches instead of all at once.
- Nothing is lost: anything queued goes out on the next pass or when you're back online.

# v1.17.3


Fixes a hang that could freeze KOReader when several queued changes — especially notes — tried to sync at once.

**Fixes**
- Queue flushes are now bounded: only a few changes are sent per pass, and the rest drain shortly after, so a long network burst can't stall the device.
- Closing a book no longer waits on a large queue; pending changes sync on the next resume, reconnect, or timer tick.
- No data is lost — anything not sent this pass stays queued and goes out on the next one.

# v1.17.2


Notifications are much easier to read, and updating is clearer.

**Notifications**
- Toasts are now wider, fixed-width cards instead of tiny boxes.
- Book names are shown in **full** (they used to be shortened to the first two words).
- A small monochrome symbol marks each notification (✓ ★ • …); choose **More → Settings → Toast symbols → Off** for plain text.
- Important results (a manual sync) now appear as a larger banner with a KOReader icon.

**Updates**
- The Version item now reads "Version: x.y.z · tap to check for updates", and changes to "Update available: x.y.z · tap to update" once a newer release is known.
- GitHub release pages now show this changelog text (instead of a bare "Full Changelog" line).
- Fixed: clearing a saved value (e.g. turning off "Remember password") now persists on device.
