# v1.4.0-beta.1 · 2026-11-14

## OrbitUI settings and Bookshelf patches

- **Custom quick actions** opens the saved list and its create button from **Dock & interface**.
- Pick the app-bar icon at **Dock & interface → Icons, fonts & shared appearance → Icons → System Icons → Tab Bar → Tab: OrbitUI**. With the picker set to **Default**, you can supply `koreader/icons/orbitui_menu.svg`.
- OrbitUI runs KOReader’s registered Bookshelf patch hooks. **Progress Bookmarks** settings appear under **Library → Advanced library settings**. **Bookshelf Bar Styles** appear in the line editor for a line containing `%bar`.
- The OrbitUI tab offers **Restart KOReader** on supported devices. Android shows **Close KOReader** and prompts you to reopen the app.

## Reader and library

- Comic archive metadata from ComicInfo now feeds Library and book information. KOReader custom fields retain priority.
- Library searches reuse normalized book text between queries.
- The reader has a compact text-selection menu, dictionary highlight feedback, native footer controls, and optional Syncery and Bluetooth HID shortcuts when available.

## Updating

Enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI** and check for updates. Reopen KOReader after installation. Stable remains on 1.3.0.

# v1.3.0-beta.1 · 2026-11-13

## One place for OrbitUI settings

- The OrbitUI grid tab sits directly beside Quick Actions in KOReader’s top menu. It replaces the separate Bookshelf settings tab and opens the shared settings from Home or from a book.
- **Home** groups the dashboard, cards and wallpaper. **Library** groups shelves, covers and themes. **Dock & interface** covers shortcuts and shared appearance. You can search across the settings.
- Long-press a dock shortcut to add, replace or remove it. **Edit dock** also lets you reorder shortcuts. Open a library profile, folder, collection or quick action right from the dock.
- Fresh setups start with **Home, Library, History and Power**. Existing docks retain their shortcuts. Manga remains available as a shortcut, and existing manga shortcuts can still open their library start menu.

## Updating

Open the OrbitUI updater, enable **Include preview releases**, and check for updates. Restart KOReader after installing. In this beta, the updater is under **OrbitUI → System & maintenance → Updates**.

The menu and dock were tested on a Bigme B7 Pro. The default dock order was tested on an emulated Kobo. The stable channel continues to offer 1.2.0.

# v1.2.0-beta.4 · 2026-11-11

## Home

- The straight cover row has clearer card borders, an aligned greeting and date, larger add and search icons, and a stronger divider below the book progress labels.
- Want to read and Recently added each have their own card and pager. Their cover stacks are larger, with more room for the covers above each label and arrow.
- The reading streak and Monday–Sunday reading chart sit beside the reading goal. They use KOReader's local statistics and are available in English and Swedish.
- The Silverfish companion and its details make better use of the space beside the current book.

## SimpleUI 3.0.3 integration

- Copy visibility settings for shared File Manager and Reader menu items.
- See a folder's name on its File Manager placeholder when no cover is available.
- Tiny Critter has updated bubble tails and shadows.

## Testing

The Home layout and both shelf pagers were checked on a Bigme. One Recently added cover briefly used a placeholder after paging and returned after restarting KOReader. The combined release was checked with local tests and upgrade checks.

Choose the **preview** channel in OrbitUI's updater to install this beta. The **stable** channel offers 1.1.0.

# v1.2.0-beta.3 · 2026-11-11

## What’s new

- **Straight cover row on Home.** Four equally sized covers show progress at a glance. The last book’s title sits below the time estimate, and the Want to read and Recently added stacks share a card with independent paging. The layout uses Inter by default and respects your custom UI font. It is preselected in the first-run setup guide.
- **An airy book information page.** See the cover, reading status, rating, description and cached EPUB tags together. The existing book actions and detailed tabs are available from the page.
- **Updated search and library tools.** Book search keeps the query, scope and sort together. Tag and similar-book results offer book and series views. Collection editing, shelf appearance and dashboard module settings have clearer layouts.
- **A clearer reader panel.** See estimated time for the book and chapter when reading statistics are available, and open KOReader’s native Reading settings directly. The Also reading tab now recovers from stale navigation state.

This beta includes the previously merged Bookshelf 6.4.2 and SimpleUI 3.0.3 integrations.

## Testing

USB testing on a Bigme covered Home, Library, Manga, book information, search, the reader panel and touch after sleep and wake. The final Inter and header alignment changes were checked with KOReader widgets on desktop. A fresh physical installation and the final typography still need device checks.

Enable preview releases in OrbitUI’s updater to install this beta. The stable channel continues to offer **1.1.0**.

# v1.2.0-beta.2 · 2026-11-10

OrbitUI 1.2.0-beta.2 brings a new reader bottom panel and more ways to discover, continue and keep track of local books.

This is a preview release. **Physical touch input after sleep/wake still needs verification with a stable connection.** Wireless ADB disconnected during that part of the Bigme tests. The release is published with this known verification gap; stable **1.1.0** remains available.

## A new reader bottom panel

- Book information, reading position and chapter progress in one panel, with clear tabs for the current book and other ongoing reads.
- Quick access to contents, bookmarks, search, book details, pinned references and Go to page. The ongoing-books tab includes paging and respects KOReader's ask-before-opening setting.
- **Reading settings…** opens KOReader's original reading controls, including margins and fonts.
- The OrbitUI panel is the default bottom-menu entry in this preview. To use the original menu, disable **Use OrbitUI as the bottom menu** under **OrbitUI settings → Integrations → Reader panel & X-Ray**.
- Optional standalone X-Ray and KOAssistant shortcuts. Automatic selection prefers an active X-Ray plugin, then KOAssistant. Choose a provider manually or hide the shortcut. The shortcut opens the plugin's own interface; opening the reader panel does not generate AI data.

## More local reading tools

- **Pinned references:** keep page locations, excerpts and images in a separate per-book drawer, with previews and explicit jumps.
- **Similar books and series:** discover local EPUBs through shared tags, with separate book and series results.
- **Next in series:** an optional Home card prepares the next local volumes without needing a server account.
- **Finish forecast:** an optional card uses available local reading statistics and reports when there is not enough data for an estimate.
- Reuse prepared series ordering to reduce repeated sorting during browsing. This is a scoped optimization; no claim of a measured whole-library opening speedup.

These features take inspiration from Aleph. The implementation builds on OrbitUI's existing integration; no Aleph code or assets are included.

## Updates and fixes

- Redesigned update panel with version comparison, expandable release notes, progress, cancellation and restart guidance.
- Fixed unnecessary horizontal scrolling in the new reader/update panels after viewport or display-scale changes.
- Fixed overlapping modal headings and Next in series preparation being left paused across native card rebuilds.
- Updated README and feature guide. Bookshelf 6.4.1 and SimpleUI 3.0.3 remain the integrated versions.

## Verification and limits

Both complete Lua/LuaJIT suites, all 43 translation catalogs, sealed-package tests, package/source checks and older-installer tests pass. Physical Bigme tests exercised tap/swipe entry, original reading settings, immediate opt-out/re-enable, reader-tool navigation, ongoing-book paging/switching, the KOAssistant chooser and compact scrolling. Update-panel actions were tested using an isolated UI fixture.

The sleep/wake input check remains open. Standalone X-Ray was not installed on the device, no AI request was generated, and these tests do not certify every device or plugin combination. Current release notes and source documentation distinguish software checks from physical testing.

## Install or update

Enable **Include preview releases** in OrbitUI's updater, check for updates and restart KOReader after installation. For manual installation, use **orbitui.koplugin.zip**, not GitHub's source-code archive. Back up settings and reading data first; code rollback does not restore older reading data.

OrbitUI replaces standalone SimpleUI and Bookshelf: disable those plugins and restart before enabling OrbitUI. X-Ray and KOAssistant are separate optional plugins.

Package SHA-256: `d7abac63c97b05e5a7b6b77d6ee3d20b9d6ebd16cc92e13eab422200e07ffd5f`

## Svenska

Ny läsarpanel med bokverktyg, pågående böcker och genväg till KOReaders vanliga läsinställningar. Dessutom kommer lokala bok-/serietips, egna läsreferenser, Nästa i serien, läsprognos och en ny uppdateringspanel. Panelen är standard i betan och kan stängas av i OrbitUI-inställningarna.

**Tryck efter vila är ännu inte färdigtestat på Bigmen**, eftersom den trådlösa anslutningen bröts. Betan publiceras med den begränsningen. Uppdatera via förhandskanalen och starta om KOReader.
