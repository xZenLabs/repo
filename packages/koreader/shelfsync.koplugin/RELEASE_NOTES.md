# 1.6.1 · 2026-10-06

- (feat) Add a Goodreads account connection check that verifies the cookie and uses the configured cookie refresher when the cookie is missing or expired.
- (fix) Allow Goodreads syncing when only Cookie Auto-Refresh URL is configured, and refresh rejected cookies after HTTP 403 responses.
- (fix) Goodreads shelf changes now send the cookies that came with their CSRF token. Without them, they could get a 404 "Page not found" page.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#161)

# 1.6.0 · 2026-10-05

- (feat) 🌟 Add a unified review composer to write a rating and/or review once and submit it to selected linked providers. 🌟
- (feat) Show the link method at the start of linked-book labels in provider menus.
- (feat) Turn on "Confirm changes to book read status" by default, so choosing a status or Remove from a provider's Update status menu asks first, and so do Hardcover OAuth sign-out and Fable and Pagebound log out. If you never changed this setting, turn it off under ShelfSync > Settings to keep single-tap changes.  
- (fix) Keep a Hardcover book's own privacy when its status changes, instead of resetting it to the account default. If ShelfSync can't read your Hardcover account or the book's current privacy, the status change is skipped instead of being sent as Public. Journal entries fall back to Private when the account default can't be read.
- (fix) Retry Goodreads automatic Currently Reading updates when a status read or CSRF bootstrap temporarily fails, instead of stopping after the book page is found.
- (fix) Allow Hardcover automatic linking to accept matching books even when extra contributor credits (such as narrators or translators) lower the author match score.
- (fix) Reconcile Fable status writes against system-list membership when book-detail status is missing or a write returns HTTP 409.
- (fix) Skip redundant Fable status writes when the selected status is already active, and run status-menu requests through KOReader's Trapper coroutine.
- (fix) Save the selected version check frequency correctly and allow intervals of 1–30 days.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#160)

# 1.5.0 · 2026-10-02

- Add Hardcover OAuth device-code sign-in, based on [hardcoverapp.koplugin PR #70](https://github.com/Billiam/hardcoverapp.koplugin/pull/70). OAuth is used when signed in; the configured API token remains available as a fallback.
- Confirm Hardcover journal writes using the mutation ID, without requiring journal-read access.
- Redact credentials, search terms, and personal content from logs while retaining safe request and error diagnostics.
- Prevent Goodreads session cookies from being sent if a request redirects to another host or an unencrypted URL.
- Reduce reader stalls when the GitHub version check encounters a slow or unreachable connection by adding short request timeouts ([#16](https://github.com/Lyfts/ShelfSync/pull/16)).


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#150)

# 1.4.4 · 2026-10-01

##### Plugin
- Show one gesture sync message listing providers being updated, followed by a combined result summary.
- Skip inactive providers from the all-provider progress gesture without showing per-provider failure popups.
- Fix Pagebound transport failures crashing while formatting error responses or being reported as authentication failures.
- Fix book syncing when Wi-Fi is turned on only when needed by waiting for it to connect before syncing.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#144)

# 1.4.3 · 2026-09-30

##### Plugin
- Fix Pagebound progress updates so page-based sync sends the absolute percentage with the current edition page, matching Pagebound's own request format. Keep both values updated when syncing by percentage too.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#143)
