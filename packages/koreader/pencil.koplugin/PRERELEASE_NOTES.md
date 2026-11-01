# 0.6.0-beta.2 · 2026-11-01

**This is a pre-release for testing.** Please try it and tell me how it goes! If something's wrong, [open an issue](https://github.com/mysticknits/pencil.koplugin/issues) and mention `0.6.0-beta.2`.

It has everything from [0.6.0-beta.1](https://github.com/mysticknits/pencil.koplugin/releases/tag/0.6.0-beta.1), plus one fix. If you're coming from 0.5.0 or earlier, read beta.1's **Before you install** first: it needs KOReader 2026.07 or newer, and you should back up your books' `.sdr` folders.

## What's new since beta.1

- A side-button highlight can now cross pages in EPUBs. Drag into the bottom-right corner to carry on onto the next page, or into the top-left corner to go back. When you lift the pen, the highlight is saved and you're back on the page you started on. This uses KOReader's "Auto-scroll when selection reaches a corner" setting, which is on by default. (#105, fixes #104)

## What to test

- Holding the side button and highlighting a passage that runs onto the next page.
- Everything on beta.1's list, if you haven't yet.

**Full changelog**: https://github.com/mysticknits/pencil.koplugin/compare/0.6.0-beta.1...0.6.0-beta.2

# 0.6.0-beta.1 · 2026-10-29

**This is a pre-release for testing.** Please try it and tell me how it goes! If something's wrong, [open an issue](https://github.com/mysticknits/pencil.koplugin/issues) and mention `0.6.0-beta.1`.

## Before you install

- **Requires KOReader 2026.07 or newer.** Stylus support is now built into KOReader, so you no longer replace `input.lua`. Just unzip `pencil.koplugin.zip` (below) into KOReader's `plugins` folder.
- **Back up your books' `.sdr` folders first.** This version saves ink in a new, much smaller format. Older versions of Pencil (0.5.0 and earlier) can't read it, and **opening a book in an older version after this one can erase its ink**. Once you've updated, please don't go back to 0.5.0 on the same books.

## What's new

**Faster writing**
- No more freezes mid-word in books with lots of ink. Saving now waits until you pause, and the save itself is about 18× faster and the file 8× smaller. (#77)
- Thick lines and highlighter strokes draw with less work. (#77)

**Fixes**
- The colour picker no longer disappears after a short hold, and the stroke after picking a colour is no longer lost. (#96, fixes #72)
- Highlighting with the side button no longer switches the pen to the eraser. (#101, fixes #85, by @hanokyu)
- Renaming a book keeps its ink and its annotation previews. (#86 by @bateast, #100, fixes #84)
- A book with ink no longer fails to open after changing the font size. (#89 by @andrew-lawlor)
- New ink is saved straight away, even in a book you're writing in for the first time. (#102)
- The page corner folds as soon as you write and lifts when you erase the last ink. (#92, #97)
- A stroke started right after picking a colour or switching tools is no longer cut short. Those confirmations now show as a small banner at the top of the screen. (#99)
- Ink is saved before the device goes to sleep. (#77)
- The plugin still loads if your file manager flattened its folder when unzipping. (#94, from @richelgomez99)

**Installing**
- Each release now comes with a ready-to-use `pencil.koplugin.zip`. (#98, closes #43)

## What to test

- Writing quickly in a book that already has a lot of ink: any lag or freezes?
- Holding the pen still to open the colour/width picker, picking a colour, then writing straight away.
- Highlighting text with the side button, then writing.
- Renaming a book that has ink, then reopening it.
- Your existing books: does all your ink still show up after updating?

## Thank you

Huge thanks to @andrew-lawlor, @bateast, @hanokyu and @richelgomez99 for their fixes, and to everyone who reported these bugs. 💛

**Full changelog**: https://github.com/mysticknits/pencil.koplugin/compare/0.5.0...0.6.0-beta.1

# 0.1.0 · 2026-01-12

Initial release of the plugin for beta testing. Please review the readme for setup instructions.
