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

# 1.4.2 · 2026-09-30

##### Plugin
- Fix Fable progress updates failing when **Auto sync by edition pages** is enabled; percentage-based syncing is unaffected.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#142)

# 1.4.1 · 2026-09-30

##### Plugin
- Refresh Fable and Pagebound account labels immediately after logging in or out.
- Improve Pagebound login feedback with separate sign-in and token-exchange stages, a longer bounded timeout for Pagebound's token exchange, and clearer transport errors. Explain why automatic tracking is unavailable and label the locally saved account without implying its session was just verified.
- Fix Hardcover sometimes failing to mark a newly linked book as Currently Reading automatically.
- Fix Hardcover note syncing.
- Prevent automatic book-status caching from using a document after it is closed or replaced while Wi-Fi is restoring.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#141)
