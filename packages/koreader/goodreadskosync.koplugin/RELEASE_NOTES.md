# v2.0.0

Release v2.0.0

# v1.26.1

- **Browse Goodreads — crash fix.** If the image cache directory was missing, pruning threw and the whole page failed ("Couldn't load the page"). Pruning is now a safe no-op and image/CSS enrichment can never fail a page. Added a regression test.
- **Browse Goodreads — better home + messages.** It opens **My Books** (`/review/list`) instead of the anti-bot-challenged root `/`, and shows clearer "sign-in required" / "blocked" messages.
- **Browse Goodreads is now experimental and dev-channel only** (hidden on stable), labelled "Browse Goodreads (experimental)…".
- **Reader-style rendering by default** (skips the site's modern CSS, which CRE can't lay out); dev toggle for Site vs Reader style.

# v1.26.0

- **Selectable update channel.** Settings, and the main-menu version label, now honour an **Update channel** preference: **Stable** (published releases) or **Dev** (prereleases from the dev branch). The default matches the channel the running build was published on; switching channels changes where "check for updates" (and the daily auto-check) fetches from.
- Both channels are now published: `v1.26.0` (stable) and `v1.26.0-dev` (dev prerelease).

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
