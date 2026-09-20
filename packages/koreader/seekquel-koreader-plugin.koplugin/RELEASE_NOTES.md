# v1.10.1

### What's new

Today's reading summary now says when it's showing your current page rather than what was last saved, so the numbers underneath it are never unlabeled.

### Install

Download `seekquel.koplugin-v1.10.1.zip` below, unzip it, and copy the `seekquel.koplugin` folder into your KOReader `plugins/` directory. If you already have the add-on installed, use its own updater (Seekquel menu → Check for update) instead — it verifies every file before replacing anything.

# v1.10.0

### What’s new

Seekquel’s actions can now be put on a gesture. Open KOReader’s Gesture Manager and five of them are waiting there beside every other action it offers: sync now, sync status, today’s reading, resume from Seekquel, and setting the book’s status. Assign them to a tap, a swipe, a multiswipe, or to a key on a reader that has buttons. Setting the status asks which of the four you mean when you assign it, so one gesture can mark a book finished without opening a menu.

Nothing is bound out of the box. A gesture fired with no book open, or on a file that is not linked to a book yet, tells you so rather than doing nothing.

Sync now also ignores a second request that arrives on the heels of the first, since a gesture is far easier to fire twice by accident than a menu item was.

### Install

Download the zip, extract it, copy the seekquel.koplugin folder into koreader/plugins, then restart KOReader.

Existing installations can update from Tools, Seekquel. KOReader versions older than v2025.08 still require the manual file copy.

# v1.9.0

### What’s new

A highlight now reaches Seekquel in the colour you painted it, matched to the nearest of the five colours the app offers. A grey highlight arrives without a colour. Highlights you had already synced are sent once more after updating, so those pick their colour up too.

### Install

Download the zip, extract it, copy the seekquel.koplugin folder into koreader/plugins, then restart KOReader.

Existing installations can update from Tools, Seekquel. KOReader versions older than v2025.08 still require the manual file copy.

# v1.8.0

### What’s new

Sync now ends with a short reading recap showing today’s minutes and pages, the chapter reached, and your current progress. Automatic syncs stay quiet. Open Today’s reading to see the recap again, or Today in Seekquel to refresh your daily targets and current streak.

When Seekquel has a later place logged from a hardcover, audiobook, another edition or another app, opening the linked book now asks before moving KOReader to the closest percentage in the local file. The move is approximate and never adds pages or reading time.

### Install

Download the zip, extract it, copy the seekquel.koplugin folder into koreader/plugins, then restart KOReader.

Existing installations can update from Tools, Seekquel. KOReader versions older than v2025.08 still require the manual file copy.

# v1.7.1


### Fixed

- **Seekquel now works on older KOReader builds, where it used to be missing entirely.**
  On any KOReader released before v2025.08, the add-on failed to load and showed nothing
  at all: no menu, no pairing screen, and no message saying why. It loaded a part of
  KOReader that only exists in newer builds, and KOReader skipped the whole add-on when
  it could not find it.

  Everything works on those builds now except the add-on updating itself, which needs
  that same missing part. The menu says a new version is ready and that it needs a
  computer to install, and tapping it explains to copy the files across rather than
  turning on wifi and failing at the end of a download.

  Found and fixed by [joelstitch](https://github.com/joelstitch).
