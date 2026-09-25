# v1.12.1

### What's new

- When the add-on cannot update itself, it now says what went wrong: the download stopped partway, arrived damaged, or could not be installed on this device, and what to try next. Before, every failure read "Could not reach Seekquel".

### Install

Download `seekquel.koplugin-v1.12.1.zip`, unzip it, and copy the `seekquel.koplugin` folder into KOReader's `plugins` folder. Restart KOReader. If the add-on is already installed and paired, it updates itself from Seekquel.

# v1.12.0

### What's new

- A book you finish in Seekquel is now marked finished in KOReader too. The next time you open it on your e-reader, KOReader's own status changes to finished. A status you set on the e-reader since always stands, and a book you are reading again is left alone.
- Sync now sends today's reading up to the page you are on. KOReader only saves its reading statistics every fifty page turns, so a sync mid-sitting could leave out the last few dozen pages. The add-on now asks KOReader to save them first.

### Install

Already using the add-on? It updates itself, so there is nothing to do.

New install: download `seekquel.koplugin-v1.12.0.zip`, unzip it into KOReader's `plugins` folder so you have a `seekquel.koplugin` folder there, restart KOReader, then pair it from the Seekquel menu with the code shown in the app.

# v1.11.0

### What's new

- Each reading day is now sent as a share of the book as well as a page count. Changing the font size partway through a book used to make the days on either side of the change describe a different book; Seekquel now credits every day the same way.

### Install

If the add-on is already installed, it updates itself from Seekquel. For a new install, download seekquel.koplugin-v1.11.0.zip, unzip it, and copy the seekquel.koplugin folder into KOReader's plugins folder, then restart KOReader.

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
