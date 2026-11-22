# v1.7 · 2026-11-22

New

Progress centre: four tabs (Progression, Quests, Ranking, Achievements). Guided tour on first opening, replayable with the "i" button. Unique public username, required to appear in the ranking. Profile picture chosen from your e-reader or online. Podium and recent reads.
Recent reads: your profile shows covers of your latest books under your stats.
Reading settings: new panel for font, size, line spacing, width and margins (Small, Medium, Large). Settings are saved in KOReader.

Fixes

Beast Novels: Premium chapters are no longer listed. "Chapter N" labels are translated.
Freezes when changing chapter: automatic translation no longer runs while reading. It happens during download or in the background. Without background tasks, the original text is shown with a message instead of freezing.
Manga batch download: chapters are saved as page images (CBZ). Before, the progress bar moved without saving anything.
Translations: missing messages added in all languages.

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
