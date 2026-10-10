# v1.7.0 · 2026-10-10

# Instapaper for KOReader v1.7.0

This release is about reading flow: finished articles leave your unread list without manual work, and it's much easier to get back to the list you were browsing.

## New

### Archive articles when you finish them
New setting: **Settings → When finished**
- **None** (default): no change.
- **Archive**: when you close an article you've finished, it's archived on Instapaper. An article counts as finished when you reached the last page, or marked it as finished in KOReader.
- **Archive + Delete file**: also deletes the downloaded file from the device, but only after the archive has succeeded.

This works offline: the article is archived the next time the device is online. Finished articles no longer stay in your Unread list at 100%.

### Return to the list from an article
For articles opened from an Instapaper list:
- **Insta button**: a small button in a corner of the page takes you back to the list, on the page you left it.
- **End of article**: the end-of-document popup offers **Back to Instapaper list**, **Go to beginning** and **File browser**.
- **Back key**: on devices with page/Back keys, Back returns to the list.

You can set all of this under **Settings → Return to list from an article**. Choose the corner or turn it off, hide the button and keep the corner tap, and turn the end-of-article popup or the Back key behaviour on or off.

### Continue where you left off
- **Continue: Unread (page 3)** appears at the top of the Instapaper menu when you used a list in the last hour. It reopens the list instantly, without a network request, on the page you were on.
- Articles you've finished in the meantime are left out, and the progress you made on the device is shown.
- New gesture action: **Instapaper: continue last list**. If there's nothing recent to continue, it opens your last used folder (or Unread) fresh from the server and tells you so.

### Load more and Refresh in article lists
- **Load more**: with API v2, lists load 50 articles at a time, with **Load more…** at the end. The title shows how many are loaded out of the total, e.g. "Unread (50/1234)".
- **Refresh**: the reload icon at the top left of a list fetches the latest data. If there are new articles it jumps to the top and says how many; otherwise it stays where you are and shows "No new articles."

## Improved

- **Settings menu**: Settings is now a regular KOReader menu. Each option shows its current value, choices are shown as a list, and changes are saved immediately.
  - **After download** is renamed **After single download**, to make clear it doesn't apply to bulk downloads.
  - **Article list limit** now applies to API v1 only.
- **Bulk download**:
  - The window opens immediately, with no wait for the server.
  - It remembers the folder you used last time.
  - Choose the folder from a list, instead of cycling through folders one at a time.
  - Archive and Delete are now a single **After download** choice. "Delete from Instapaper" makes clear that it deletes on the server, not on the device.
  - Folders are fetched only when you tap **Folder**, so newly created folders always show up.
- **Archive and Delete in a list**: archiving or deleting from the long-press menu no longer jumps back to the first page, and custom folders keep their name in the title.

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
