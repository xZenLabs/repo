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
