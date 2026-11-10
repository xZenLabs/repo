# v1.6.1 · 2026-11-10

### Fixes
- **Library**: manga you've read or downloaded now show up in the Manga tab, no need to add them to favourites. Ones you'd already started are picked up the first time you open the library (the exact title comes back when you open the manga's page).
- **Sleep**: after your e-reader goes to sleep, you no longer have to restart it to reopen the plugin.

### New
- "Manga · Auto-add to library" option in Settings, to turn this off.

# v1.6 · 2026-11-08

### New

- **10 new extensions**: NovelFull, NovelNinja, BeastNovels, Blume-Verse, Azora Manga, Cenele, RewayahFans, SeaNovel, IxDzs8, Linovelib
- **Reading speed (words/min)**: measured while reading in the built-in reader, from pages actually read (not a sleeping device, not a skimmed page). Details in the progress centre, can be turned off in Settings.
- **Leaderboard**: your stats (pages read, chapters, streak, words/min) are shown in the ranking and in a friend's menu.
- **Novel reader**: option to hide the chapter title (the back arrow and the gear stay, the text gets the room). Asked on first opening, changeable in Settings and in the reading settings.
- **Chapter list**: opens on the page of the chapter you are reading (option in Settings).

### Changes

No more sources bundled in the plugin: all of them are downloaded from Sefirah Source Hub (Sources tab › “Refresh the catalogue”, Wi-Fi required). The plugin is much lighter. Sources already on your e-reader keep working. Catalogue icons show up right in the Sources tab, and sources you had installed are restored automatically when the catalogue refreshes (if a plugin update wiped them).

# v1.5 · 2026-10-28

## English

### New
- **Sources**: the tab reads the Sefirah Source Hub catalogue. Tap the install icon to download and install a source, no manual copying. The antenna icon offers "Refresh the catalogue" or "Receive with a code". An "Update" button shows in the settings of a Hub source when a newer version exists.
- **New extensions**: LNCrawler, MyDramaNovel, WordRain.

# v1.4.1 · 2026-10-25

Fixes

Novelfire: the site now redirects to novelphoenix.com through a JavaScript page that KOReader can’t follow. Sefirah now follows the redirect, and chapters open again.
Novelfire: already downloaded (broken) chapters are removed from the cache on first launch. Library and progress are kept.
Novelfire: more robust extraction, and on failure the site’s response is saved to sefirah/novelfire_last_error.txt.
Opening Sefirah: fixed a name conflict with other plugins (“attempt to call method ‘get’”, ui/library.lua).

New

TruyenDichAI extension, with its icon.

# v1.4 · 2026-10-24

Sefirah v1.4

New
Progress center: XP, levels, quests (daily, weekly, monthly) and achievements (easy, medium, hard).
"i" button (top right): explains every way to earn XP and how levels work. Also shown on first open.
XP for manga: 2 XP per page and 10 XP per chapter (novels: 5 and 20).
Community leaderboard, friends and profile picture.
New source: MangaBall.
Night mode for the whole plugin.
New icons in settings.

Improvements
Changes made to the WEBTOON source files.
Smoother and faster: disk writes batched (settings, library, reading progress), lighter quest checks on every page turn, more responsive download tracking.
Reading settings: you now return to the same page of the chapter (no longer page 1).
Updated translations.

Removed
AniList integration and the old reading statistics screen.
