# 1.4.4

##### Plugin
- Show one gesture sync message listing providers being updated, followed by a combined result summary.
- Skip inactive providers from the all-provider progress gesture without showing per-provider failure popups.
- Fix Pagebound transport failures crashing while formatting error responses or being reported as authentication failures.
- Fix book syncing when Wi-Fi is turned on only when needed by waiting for it to connect before syncing.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#144)

# 1.4.3

##### Plugin
- Fix Pagebound progress updates so page-based sync sends the absolute percentage with the current edition page, matching Pagebound's own request format. Keep both values updated when syncing by percentage too.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#143)

# 1.4.2

##### Plugin
- Fix Fable progress updates failing when **Auto sync by edition pages** is enabled; percentage-based syncing is unaffected.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#142)

# 1.4.1

##### Plugin
- Refresh Fable and Pagebound account labels immediately after logging in or out.
- Improve Pagebound login feedback with separate sign-in and token-exchange stages, a longer bounded timeout for Pagebound's token exchange, and clearer transport errors. Explain why automatic tracking is unavailable and label the locally saved account without implying its session was just verified.
- Fix Hardcover sometimes failing to mark a newly linked book as Currently Reading automatically.
- Fix Hardcover note syncing.
- Prevent automatic book-status caching from using a document after it is closed or replaced while Wi-Fi is restoring.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#141)

# 1.4.0

##### Plugin
- Prevent title auto-linking from selecting unrelated search results by checking title and author similarity. Wikipedia and WikiReader EPUBs are excluded from linking and syncing.
- Add Pagebound sync support with email/password login, book linking, status updates, and page/percentage progress sync.
- Pagebound notes are published to the linked book's forum with a title showing progress and page position.
- Fixed on-demand Wi-Fi shutting off while provider requests were still running; restored Wi-Fi now stays on until all queued operations finish.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#140)
