# v2.0.0 · 2026-11-07


The silverfish has company. This version brings the brood (more than one creature in the same save, one awake at a
time) and the first new species, the Ash Cat.

The brood and the Ash Cat:

- New: the **brood** (the ☰ menu on the creature's screen → **BROOD**). Your silverfish can share the save with
  other creatures, one awake at a time. A sleeping creature's clock stops: no hunger, no ageing. Your reading
  memory (books, bookshelf, streaks) goes with whoever is awake, and each creature keeps its own stage, mood,
  personality, diary and lineage.
- New: the **Ash Cat**, the second species. Its egg is ready from the start: tap it on the brood screen to hatch
  it, and your silverfish goes to sleep until you wake it again. The cat descends from cats who pulled pages out
  of the furnaces, one at a time, in their teeth. It doesn't eat your pages; it keeps them. It has its own stages
  (egg, kitten, adult, elder), its own stash bar, diary (CELLAR NOTES), achievements, last words and lineage, and
  its own voice for everything the silverfish says: everyday lines, reactions to how you read, the 16 literary
  influences, its temper, the lines it puts together on its own, dreams, chapter comments, comments on your
  highlights and a vocabulary for each theme. It quotes the Rules of the Cellar, which its grandmother taught it.
- New: the **brood screen** shows the awake creature's life (name, species and stage, obsession and marked
  traits, the book you're reading, days, books and generation) and the crew: sleeping creatures, eggs ready to
  hatch and locked slots.
- New: **names.** Give each creature a name (up to 14 characters, or shuffle a suggestion) on the welcome screen,
  after it hatches, or in the settings (**Name…**). The name is the title of its screen.

Screens:

- New drawings for the silverfish and the cat, in black and white and in colour. On a colour screen, the drawings
  and the sleep screen are in colour.
- The **ARCHIVE** button is now a menu (☰): the creature, the brood, the notebook, the diary, achievements and
  the lineage.
- New: a **gear** button at the top of the creature's screen opens the settings. Long-pressing the creature still
  opens them too.
- New: **Open at startup** and **Gesture shortcut** can now be turned on or off in the settings. Before, they
  could only be chosen on the welcome screen.

Home screen:

- New: with Bookshelf 6.1 or newer, the welcome screen's **Home screen card** option also puts the creature on
  Bookshelf's home shelf, so there are no manual steps.
- Bookshelf card, by [AndyHazz](https://github.com/AndyHazz)
  ([pull request](https://github.com/theusmaoliveiras/silverfish-koreader/pull/2)): ready for Bookshelf 6.1.
  The card is drawn once at its own size, refreshes only when the creature or its thought changes (no needless
  e-ink flashes), and sits centred among the covers on a cover shelf. Older Bookshelf versions still work.

Fixes:

- Fixed: with Simple UI 3, the welcome screen's **Home screen card** option didn't put the card on the home
  screen. Now it adds it at the end of the first page, or takes it off.
- Fixed: Silverfish kept counting pages with KOReader's reading statistics turned off (for example by a
  profile). Now it follows that setting.

Your silverfish keeps its progress: an older save opens as a brood with your silverfish awake. To update, replace
the `silverfish.koplugin` folder (see "Updating and backups" in the README), or update from Storefront.

**Install:** download `silverfish-v2.0.0.zip` below, unzip it, and copy the `silverfish.koplugin` folder into KOReader's `plugins` folder.

# v1.1.0 · 2026-10-31

- New: a Silverfish card for the [Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) plugin. Put it in the top panel or stand it on a shelf among your books. Narrow, it's just the silverfish; wider, it gets a speech bubble with what it's thinking. Tap it to open its screen. Tested with Bookshelf 6.0.4.

Your silverfish keeps its progress: to update, replace the `silverfish.koplugin` folder (see "Updating and backups" in the README), or update from Storefront.

**Install:** download `silverfish-v1.1.0.zip` below, unzip it, and copy the `silverfish.koplugin` folder into KOReader's `plugins` folder.

# v1.0.0 · 2026-10-30

**Lives in your e-reader. Eats what you read. Judges your taste.**

First public release of Silverfish, a KOReader plugin.

### Install

1. Download `silverfish-v1.0.0.zip` below and unzip it.
2. Copy the `silverfish.koplugin` folder into KOReader's `plugins` folder (Kindle: `koreader/plugins/`, Kobo: `.adds/koreader/plugins/`, Android: `koreader/plugins/`).
3. Restart KOReader.

If you tested the beta (`traca.koplugin`), delete that folder first. Your silverfish keeps its progress.

### What's in it

- A silverfish that hatches, eats the pages you read and grows through four stages (nymph, young, adult, elder), with generations and a family lineage.
- A personality shaped by your reading: 16 literary influences, picked up from the text of your books and from their EPUB genre tags, plus traits from your habits.
- It notices characters, words, places and events, comments on chapters and reviews the books you finish.
- Diary, notebook of your highlights, achievements, bookshelf and lineage.
- Sleep screen with dreams about your reading, and a sleeping pose for each stage.
- Optional card and button for the Simple UI plugin.
- English and Portuguese. No AI, no internet.

Tested on KOReader 2026.07.1 on a Kindle Paperwhite 11. Reports from other devices are welcome in Issues.

Full list of changes: [CHANGELOG.md](https://github.com/theusmaoliveiras/silverfish-koreader/blob/main/CHANGELOG.md).
