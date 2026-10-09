# v1.19.0 · 2026-10-09

## v1.19.0

### New: Feedbin accounts
- Add a `feedbin` account. It signs in with your Feedbin email and password.
- Feedbin tags show as folders. A feed with several tags appears in each of them.
- The account's top level has **★ All Feeds**, **★ All Unread** and **★ Starred**.
- You can mark stories read or unread and starred or unstarred.
- *Mark all as read* works on feeds, folders, the whole account and the ★ feeds.
- Unread counts fill in over a few refreshes and show as e.g. `(12+)` until they are complete.

### New: Feedbin article extraction
- A new sanitizer type, `feedbin`, fetches the full article for Feedbin stories. It needs no token and has no quota.
- Stories from other accounts skip it and go to the next sanitizer.
- It is off by default. To turn it on, set `active = true` for it in your configuration.

### Fixes
- Titles with an apostrophe or `&` no longer show `&#39;` or `&amp;` in the title or the saved file's name.
- A title made only of punctuation no longer becomes a hidden `.html` file.
- A very long title no longer makes opening the article fail. Filenames are now capped at 64 bytes.
- After the RSS button in an article, Back now goes up through the feed's folder instead of straight to the account list.
- Tapping an account on that list no longer closes the article underneath.

Thanks to @anthonyfelts for this release (#18).

# v1.18.0 · 2026-09-27

### New

- A refresh icon in the top-left corner of feed and article lists (or the Menu key on devices without a touchscreen) reloads the list without leaving the plugin.
- On lists that support it, that same icon opens a small menu with "Refresh" and "Mark all as read".
- You can long-press any feed or folder and pick "Open on startup" so the plugin opens straight to it.
- In the article preview, turning the page past the last page opens the next article, and turning back from the first page opens the previous one. You can change this under Settings > Page keys at article edges.
- The article preview has a new "Previous" button for devices that only have a touchscreen.
- The dialog at the end of an article now has "Next" and "Next unread" buttons, so you can go on to the following article without going back to the list.

### Fixed

- "Mark all as read" now works for FreshRSS feeds, folders and whole accounts. Before, they stayed unread.
- If your login is rejected, the plugin now stops instead of retrying forever.
- Leaving the RSS list now closes the article that was open under it, so you're no longer stuck going back and forth between the two.
- Two articles opened quickly one after another no longer break each other's images.

# v1.17.2 · 2026-09-22

## v1.17.2 — Designed EPUB covers

Saved articles now get a cover of their own instead of a bare lead image.

- **Painted cover** — the article title on top, the lead image cropped into a
  landscape band in the middle, and the byline plus feed name at the bottom.
- **No image, still a cover** — articles without a usable picture get a
  text-only cover with larger type, so nothing lands in the library as a blank
  tile.
- **No extra downloads** — the cover reuses the image already picked for the
  article; it is fetched once and packed into the EPUB as before.

On by default. Turn it off under **Settings → Designed EPUB cover** to keep the
previous plain lead-image cover; if a cover cannot be painted for any reason,
the plugin falls back to that automatically.

## v1.17.1 — Sanitizer fixes

- **Diffbot is usable again** — its wait was cut short by the wrong timeout, so
  most successful extractions never arrived; the timeout now follows Diffbot's
  own page-fetch budget.
- **Diffbot rate limit handled** — a 429 from the free plan is retried once
  after the wait the server asks for, instead of silently falling through to
  the next sanitizer.
- **Plain-text and list pages** — Diffbot responses that carry only a `content`
  field were read as empty; they now come through.
- **RSS links with entities** — `&amp;` and `&#038;` inside `<link>` are decoded
  like every other field, fixing the ~4% of feed links that opened broken.

## v1.17.0 — Metadata, speed and FreshRSS favourites

- **Richer saved EPUBs** — author, description, cover image and a real chapter
  list are filled in from data already downloaded, at no extra request.
- **Parallel image downloads** — an article's images are fetched by several
  worker processes at once instead of one after another.
- **FiveFilters via RapidAPI** — replaces the discontinued free service, with a
  monthly request cap so the plan is not overrun.
- **FreshRSS favourites** — star and unstar articles, browse them in a Starred
  feed, and see the star in the list.
- **FreshRSS 404 fix** — the error that hid every feed on some servers is gone.

# v1.17.1 · 2026-09-21


## v1.17.0
- **Faster article downloads.** Images in an article are now fetched in parallel
  (4 at a time) instead of one after another, so opening an image-heavy article
  is noticeably quicker. You can still cancel mid-download.
- **FreshRSS favourites.** Star and unstar articles from FreshRSS, and browse
  everything you've starred in its own list — the same way the other backends
  already worked.
- **Fixed: FreshRSS showed no feeds.** Opening a feed or folder returned a 404,
  which left the feed list empty. Feed and folder browsing works again.

## v1.17.1
### Fixed

- **Diffbot now returns content instead of silently timing out.** It extracts
  server-side and answers only when done — typically 4–23 s — but the plugin
  gave up after 8. It now waits for Diffbot's own budget (`timeout`, default
  30000 ms). Fast articles still open as fast as before.
- **Diffbot rate limiting is handled.** The free plan allows about one call
  every 10 s and rejects the rest with `429`, which was treated as a failure.
  The plugin now honours `Retry-After` once before falling through, and the
  wait can be cancelled with a tap. Six articles opened in a row used to give
  one success; now they all succeed.
- **Non-article Diffbot responses** (section and index pages) are no longer
  discarded as empty.
- **Feed links with escaped characters** no longer produce broken URLs. RSS
  item links skipped the entity decoding that titles and Atom links get,
  affecting 4% of links across 26 live feeds.

### Changed

- Request timeouts are now enforced across all sanitizers and the direct
  article download; the total-timeout setting previously had no effect.
- The README documents the measured speed gap: Diffbot is ~3× slower than
  Instaparser and rate-limited on the free plan, so listing Instaparser first
  is usually the better default.

# v1.17.0 · 2026-09-21

## What's new

- **Faster article downloads.** Images in an article are now fetched in parallel
  (4 at a time) instead of one after another, so opening an image-heavy article
  is noticeably quicker. You can still cancel mid-download.
- **FreshRSS favourites.** Star and unstar articles from FreshRSS, and browse
  everything you've starred in its own list — the same way the other backends
  already worked.
- **Fixed: FreshRSS showed no feeds.** Opening a feed or folder returned a 404,
  which left the feed list empty. Feed and folder browsing works again.
