# v1.6.0 · 2026-10-09

# Instapaper for KOReader v1.6.0

## Highlights

### Instapaper API v2 and access token login

- The plugin now uses **Instapaper API v2** by default. API v1 is still available as a fallback.
- **New login method: personal access token.** Generate a token for your application at
  <https://www.instapaper.com/developers/applications>, paste it in **Log in → Access token**, and you're done.
  You don't need a password, consumer key or secret. The username shows in the **Log out** entry.
- Logging in with email and password (xAuth) still works. Instapaper stops accepting **new** xAuth logins on
  **30 September 2027**, so we recommend switching to an access token.
- **No more 500-article limit:** v2 lists are paged, so long Unread, Archive and folder lists load in full.
- **Better author metadata:** v2 returns the article's byline, so it goes straight into the book metadata.
  Before, the plugin only got a byline when it found one in the article HTML.
- New setting: **Settings → API** to choose **v2** (default) or **v1**. v1 needs an email and password login,
  because an access token works with v2 only.

## Upgrading from 1.5

Nothing to do. You stay logged in, because the token from your old email and password login also works with
API v2. If Instapaper rejects that token on v2 before v2 has worked once, the plugin switches to API v1 by itself
and asks you to try again. You can also switch by hand under **Settings → API**.

# v1.5.0 · 2026-09-10

- Add bidirectional reading progress sync.  Thanks to @emes81

# v1.4.0 · 2026-08-25

- show popup on bulk download process
- name downloads after the article title, without the bookmark id 
- add author, excerpt, cover and chapters to downloaded articles

# v1.3.3 · 2026-07-20

- fix: don't crash on non-http(s) image URLs
  Articles can contain `<img src="file://...">` or other non-web schemes
  (leftover from broken exports); socket.http has no handler for these
  and throws uncaught, crashing the reader. Reject unsupported schemes
  in resolveUrl and wrap http.request in pcall as a backstop.

# v1.3.2 · 2026-06-06

- fill author field for HTML and epub output file
