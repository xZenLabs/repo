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

# v1.17.0

## [1.17.0] - 2026-09-29

Reliability fixes, and your Goodreads password is now saved by default so you don't have to sign in again.

**Sign-in**
- "Remember password" is now **on by default**. Turn it off in **More → Settings → Remember password** to delete the saved password; it's encrypted when possible and plain text otherwise.

**Fixes**
- Deleting saved data now actually persists on device — "Forget saved password" (and clearing the selected provider) previously left the value on disk.
- A sync and a queue flush can no longer run at the same time, so a queued note or progress update can't be posted twice.
- Queued items that fail during a sync now surface the retry notice too.
- Note queue keys are guaranteed unique (seeded random + counter), and the retry backoff uses its full schedule before giving up.

# v1.16.0

## [1.16.0] - 2026-09-29

Notes are now saved on the device first and posted one at a time in order, and failed syncs are kept so you can retry them.

**Notes**
- Adding several notes no longer loses all but the last one: each note gets its own queue slot and they sync in the order you added them (FIFO).
- Notes are always stored locally first, then posted; offline notes go out automatically when you reconnect.

**Failed syncs**
- Failed changes are no longer silently removed — they are kept and listed under **More → Waiting to sync**.
- New **More → Retry failed syncs**, plus a **Retry failed** button in the Waiting to sync dialog.
- Only one sync flush runs at a time, so a note can't be posted twice.

# v1.15.0

## [1.15.0] - 2026-09-24

A new **Reading** section in the main menu brings your Goodreads Reading Challenge onto the device.

**Reading challenge**
- Shows your annual goal, how many books you've read, the percentage, how many days are left, and whether you're ahead of or behind schedule.

**Change reading goal**
- Set or update your annual goal from KOReader, no need to open the website.

**Reading stats**
- A year-by-year list of how many books you've finished, with a total.

All three are read/one-tap actions and do not change how existing sync, linking, notes, ratings, or shelves work.

# v1.14.0

## [1.14.0] - 2026-09-24

The menu is tidier: the everyday actions stay up front, and the rest moved under **More**. Linking a book by hand is now one consistent flow. And there's a gentle, occasional reminder that you can support the project.

**Menu**
- Main menu: **Sync now**, **Set status on Goodreads**, **This book**, **Test connection**, **Version** (tap it to check for updates), **More**, and **Support this project** at the bottom.
- **More** now holds **Account**, **Settings**, **Sync status**, **Waiting to sync**, and **Clear failed syncs**.
- **Test connection** moved to the main menu; the version entry now checks for updates when tapped.

**Linking a book**
- "Find on Goodreads" opens a small menu with **Find manually** then **Find automatically**.
- **Find manually** — and the "Couldn't link this book" screen — open the same prompt for a title, author, ISBN, or Goodreads ID.
- The separate "Enter ISBN", "Enter Goodreads ID", and "Change linked book" entries were removed since they all did the same thing, and the book-status screen's "Change book" now uses the same prompt.

**Support**
- After a successful sync, a small, non-intrusive reminder about supporting the project appears at most once every two weeks. Turn it off in **More → Settings → Support reminders**.
