# v1.18.0 · 2026-11-08

### What's new

- Stop or start syncing a book from the Seekquel menu. "Stop syncing this book" and "Start syncing this book" do what the switch on the book's page in Seekquel does, without leaving the reader.
- A book you switched off in Seekquel says so when you open it, the Seekquel menu reads "Seekquel (off for this book)", and Sync now and Sync status tell you nothing is kept for it.
- A book you finish or rate while syncing is off is sent once syncing is back on, and its file details wait instead of being sent over and over.

### Install

Already paired? The add-on updates itself: open Seekquel in KOReader's menu and accept the update when it is offered.

New install: download seekquel.koplugin-v1.18.0.zip below, unzip it, and copy the seekquel.koplugin folder into KOReader's plugins folder. Restart KOReader, then open Seekquel from the menu to pair.

# v1.17.0 · 2026-11-03

### What's new

- The stars you give a book on KOReader's status page now reach Seekquel. Rate a book there and the rating is sent with the next sync. Before this, only a rating chosen from the Seekquel menu was sent. A rating already in Seekquel is never overwritten by a star you gave earlier, and taking a star away on the device clears nothing there.

### Install

Already paired? The add-on updates itself: open Seekquel in KOReader's menu and accept the update when it is offered.

New install: download seekquel.koplugin-v1.17.0.zip below, unzip it, and copy the seekquel.koplugin folder into KOReader's plugins folder. Restart KOReader, then open Seekquel from the menu to pair.

# v1.16.0 · 2026-10-14

### What's new

- Putting a book on hold in KOReader now pauses it in Seekquel instead of marking it Did not finish. Picking it up again carries on with the same read, so your place and the time you have already spent on it stay together. Books you put on hold before this update are left as they are until you change their status again.

### Install

Already paired? The add-on updates itself: open Seekquel in KOReader's menu and accept the update when it is offered.

New install: download seekquel.koplugin-v1.16.0.zip below, unzip it, and copy the seekquel.koplugin folder into KOReader's plugins folder. Restart KOReader, then open Seekquel from the menu to pair.

# v1.15.1 · 2026-10-14

### What's new

- **Sync no longer says "Sync complete" for a book Seekquel has not matched yet.** If the book you are reading is not linked to a Seekquel book, Sync now tells you to choose which book it is, because nothing is sent until you do. If Seekquel could not be reached to look the book up, it says your reading is still waiting to sync instead.

### Install

Already using the add-on? It updates itself; open the Seekquel menu in KOReader and accept the update.

Installing for the first time: download `seekquel.koplugin-v1.15.1.zip`, unzip it, and copy the `seekquel.koplugin` folder into KOReader's `plugins` folder on your e-reader. Restart KOReader, then pair from the Seekquel menu.

# v1.15.0 · 2026-10-10

### What's new

- **Continuing from Seekquel lands in the right place in the chapter.** When you accept "Continue there" for a place you reached in the Seekquel app, KOReader now opens the same point in that chapter instead of a percentage of the whole book. This works when your file lists the same chapters as the one you read in the app; otherwise the percentage is used as before.
- **Seekquel learns how far into the chapter you are.** Each sync now says how far through the current chapter you have read, so the Seekquel app can open the same point in it.
- **Fixed:** the offer to continue from Seekquel showed two percent signs ("60%%"). It now reads "60%".

### Install

Download `seekquel.koplugin-v1.15.0.zip`, unzip it, copy the `seekquel.koplugin` folder into `koreader/plugins` on your reader and restart KOReader. Then open Tools, Seekquel, Connect this device. If the add-on is already installed, it updates itself from the Seekquel menu.
