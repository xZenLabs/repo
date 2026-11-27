# v1.5.0-beta.7 · 2026-11-27

### Faster Hardcover linking

If your books already contain a Hardcover edition ID, OrbitUI can now link up to 25 editions in one request. The same request retrieves the book details, including page counts, publication year and ratings.

In **Settings → Integrations → Hardcover**, choose **Auto-link all books → Auto-link editions** to link books that are still unlinked. To check the entire library, choose **Re-scan all books with edition IDs → Auto-link editions**. This also corrects links pointing to a different edition. Matching links are checked locally. If Hardcover leaves an edition out of a batch, OrbitUI retries it individually.

On a Tolino Vision Color emulator with simulated Hardcover replies, linking 25 EPUBs went from **50 requests and 66 seconds in beta 6** to **one request and 11 seconds with this release ZIP**. A repeat scan made zero requests. A separate 1,000-book test of the batch lookup took about 18 minutes and 40 requests. Checking those 1,000 links again took 37 seconds with zero requests. Times on a physical reader and the live service will vary.

# v1.5.0-beta.6 · 2026-11-27

### Check Hardcover links across your library

Open **OrbitUI settings → Integrations → Hardcover book information → Re-scan all books with edition IDs → Auto-link editions**. OrbitUI compares each book’s embedded Hardcover edition ID with its saved link, creates missing links and corrects links that point to the wrong edition. The report also counts books that already match and books without an edition ID. Previously this menu only checked unlinked books.

The regular auto-link action still starts with unlinked books. Its confirmation now explains that a first pass on a large library can take hours. An edition ID avoids a title search, but new links still need Hardcover lookups and book details.

### Bookshelf 6.6.1 and SimpleUI 3.1.1

- Page counting moves on if rendering one book stalls for five minutes. KOReader menu search also handles accented and other multibyte characters when a book preview is shortened.
- The finished-books list shows the author ahead of the dates and offers a button for book actions. Tabs have larger default labels and more vertical spacing. French, Polish and Simplified Chinese translations have been updated.

To install, enable **Include preview releases** in **OrbitUI → System & maintenance → Updates**, check for updates and restart KOReader after installation. For manual installation, download **orbitui.koplugin.zip**.

# v1.5.0-beta.5 · 2026-11-25

### Pick how your current books look on Home

Hold the ongoing-books card and choose **Ongoing book display**. **Cover fan** places your selected book in front. Swipe through the fan or tap a smaller cover to bring it forward. **Book in focus** pairs a large cover with the author, reading progress and time remaining. **Straight cover row** keeps several books side by side. If you use Silverfish, the footer can also show your pet’s reading days, books and generation.

Fresh installations start with Cover fan. If you already have OrbitUI and your Reading dashboard is off, a one-time invitation shows a screenshot before you choose whether to add it. Existing dashboard users keep their chosen layout.

### Dock, shelves and dashboard fixes

- Hold a dock shortcut to make its destination your startup view.
- Large Library and Manga shelves reuse sort orders and book details across visits and background index refreshes.
- Fixed a redraw error that could leave part of Home visible again beneath the dock after replacing a dashboard card. BookOrbit achievement medals now blend into the card in day and night modes.

The book displays and Silverfish footer were tested on a physical HiBreak. The invitation was tested in Swedish and English in KOReader on an emulated Tolino Vision Color, including a 600 × 800 screen.

To install, enable **Include preview releases** under **OrbitUI → System & maintenance → Updates**, check for updates and restart KOReader after installation. For manual installation, download **orbitui.koplugin.zip**.

# v1.5.0-beta.4 · 2026-11-25

### Dashboard long presses

Long-press a card to open its usual menu. Choose **Replace module…** to swap the card in place. **BookOrbit achievements** is on the first screen of the picker. Holding a book cover still opens its book actions.

### A sun for Day Mode

When night mode is active, the button for switching back to Day Mode shows the Solar Colour sun. You can pick separate icons for Day Mode and Night Mode. An existing Day Mode choice takes precedence.

### Library search and finished books

- Bookshelf search now matches uppercase and lowercase accented and Cyrillic letters. Searching for `ångström` finds `ÅNGSTRÖM`.
- Two finished books that share a partial file checksum keep separate entries. Moving one or marking it as reading again keeps the other book’s completion record.

Verified in Swedish KOReader on an emulated Tolino Vision Color. Physical HiBreak testing is still pending.

To update, enable **Include preview releases** under **OrbitUI → System & maintenance → Updates**, check for updates, install and restart KOReader. For manual installation, download **orbitui.koplugin.zip** below.

# v1.5.0-beta.3 · 2026-11-24

### Swap a dashboard card in place

Long-press the heading or background of a card in the Reading dashboard, then choose its replacement. It keeps the same position and size. To bring back a built-in card, long-press its replacement and choose **Restore**.

### Cards adapt to their space

Book grids show more covers as a card grows. Small cards use short progress labels, clocks prioritize their first visible item, and action shortcuts show their icons. Fixed-size plugin widgets scale to fit, with taps mapped to their buttons and covers.

### BookOrbit achievement medals

The Home card and the achievement catalogue display BookOrbit’s icons and rarity colors. A small card can show three medals across or two in a vertical list. A larger card can show more when the data is available. Tap the card to browse earned and locked achievements. This uses your existing BookOrbit plugin connection.

Tested in KOReader on an emulated Tolino Vision Color with 66 modules and shortcuts at three sizes. The same seven test books produced rows or grids of three, four and seven covers. A tap selected the expected book at each size. Physical HiBreak testing of these changes is still pending.

To update, enable **Include preview releases** under **OrbitUI → System & maintenance → Updates**, check for updates, install and restart KOReader. For manual installation, download **orbitui.koplugin.zip** below.
