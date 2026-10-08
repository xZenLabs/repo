# Offline Translate for KOReader

A [KOReader](https://github.com/koreader/koreader) plugin that translates what
you select with a neural machine translation engine running **on your device**,
and shows the result in a bubble anchored to the selection.

No cloud service, no account, no text leaving the device.

<img src="docs/screenshots/bubble.png" alt="A Polish paragraph on an e-ink
screen with its English translation in a bubble above the selection" width="380">

> **Status: released.** [v0.6.0](https://github.com/fundacja-reborn/offlinetranslate-koplugin/releases/latest)
> is out, and the plugin is in daily use. The leading zero is deliberate:
> nothing here is expected to move, but the plugin sits on somebody else's API
> on both sides and has to keep working across KOReader releases, so the version
> stays below one until both have been quiet for a while.

**[What it does](#what-it-does-and-what-it-deliberately-does-not) ·
[Requirements](#requirements) · [Install](#install) ·
[Configuration](#configuration) ·
[Why it works this way](#why-it-works-the-way-it-does) ·
[Changelog](CHANGELOG.md)**

## What it does, and what it deliberately does not

| Gesture | Handled by |
| --- | --- |
| a long press on a word | KOReader's built-in StarDict dictionaries, untouched |
| a selection you drag out | this plugin: "Translate (offline)" in the selection menu |

The gesture decides, not the length of what you selected: dictionaries are better
at a word you hold down, and a model is better at the thing dictionaries handle
badly - a phrase or a whole sentence. The plugin does not replace KOReader's
dictionary path, does not override the built-in `Translator`, and does not change
what a long press does. It adds one button.

Translating a word and marking one are separate questions. The plugin can
underline words you have looked up before, which needs no translation at all,
only the knowledge that you looked them up. That is opt-in and described further
down.

<img src="docs/screenshots/selection-menu.png" alt="KOReader's selection menu
with Translate (offline) added next to the built-in Translate button, everything
else unchanged" width="380">

That is the whole footprint in the selection menu: one entry, immediately after
the one KOReader already had, which is still there and still does what it did.

When a translation is too long for a bubble, or the selection leaves no room for
one, it opens in a full window instead - carrying the original text, because at
that size the page underneath is hidden and the sentence you asked about is the
thing you need to compare against.

<img src="docs/screenshots/modal.png" alt="A long translation shown in a full
window, with the original Polish text below it under the heading Original"
width="380">

### No menu in between: the translation arrives as you let go

Letting go of a selection goes straight to the translation, in a bubble over the
sentence it came from. That is what happens out of the box: translating is what
you dragged the selection out for, and the menu in between asks a question you
have already answered.

If you would rather have the menu, **Tools → Offline translate → "After dragging
out a selection" → "Open the selection menu"** puts it back, and the plugin
becomes one more entry in it.

Nothing is taken away either way. A long press still opens your dictionary,
everything the plugin does not claim still opens the usual menu - an existing
highlight you tapped, a selection longer than the limit, a translation that
failed - and every translation carries a **Selection menu** button, so
highlighting, copying or a note is one tap from the bubble.

One thing it cannot override. If you have set KOReader's own action for a
finished selection to something other than "Ask with popup dialog" (**Settings →
Taps and gestures → Long-press on text**), that setting wins and this one does
nothing. You chose it on purpose; a plugin has no business undoing that.

<img src="docs/screenshots/selection-action.png" alt="The setting, with two
options: Open the selection menu, and Translate right away" width="380">

## Reading in a language you are still learning

The reason this plugin exists is a page you cannot quite read unaided: close
enough to follow, far enough to keep stopping. That is the situation
comprehensible input describes - understanding most of it from context, with
just enough help for the rest - and it is also the situation in which a
dictionary entry for one word out of a five-word idiom is no help at all.

Three things follow from it. The first two are on out of the box, and either can
be switched off in **Tools → Offline translate**.

### Phrases you have looked up before are underlined

Translate a phrase once and it gets a faint dotted underline wherever it turns
up again - not only in the book you were reading at the time. The plugin
remembers translations across books, so an expression met in one novel is marked
when it appears in the next.

<img src="docs/screenshots/marked-phrases.png" alt="A page of an English novel
on an e-ink screen. Several phrases carry a faint dotted underline, two of them
twice on the same page, and a small bubble over one of them shows its Polish
translation above a button reading Learned" width="380">

That recurrence is the whole point. Meeting an expression again, recognizing
that you have met it before, and eventually finding you no longer need the
translation is what learning by reading actually looks like - and it is the part
a translation window cannot do for you, because it happens between the lookups
rather than during one.

Tapping an underlined phrase brings its translation straight back, with nothing
to select first. The bubble carries **Learned**: that forgets the phrase and
takes its underline out of every book at once. It is deliberately not called
"delete" - forgetting is what the plugin does, while what you are doing is
saying you are done with this one.

Everything else about a tap is unchanged. Tapping anywhere that is not an
underlined phrase turns the page exactly as before, and a highlight you made
yourself still opens KOReader's own menu, even where a phrase is marked
underneath it.

### So are words you keep having to look up

A word you hold down goes to your dictionaries, which are better at single words
than any translation model. But the plugin can notice that you looked one up, and
underline it the next time it turns up.

<img src="docs/screenshots/marked-words.png" alt="A page of Three Men in a Boat
on an e-ink screen, with seven faint dotted underlines: four under single words
and three under phrases, one of which runs across a line break" width="380">

A word you looked up and a phrase you translated get the same underline, and a
tap does the same thing to both: it brings back what you got last time. Only the
source differs - your dictionary for one, the translation server for the other -
and you do not have to know which is which to use them.

Every dictionary lookup you make is counted, from the moment the plugin is
installed. Nothing about looking a word up changes: the same long press, the same
popup, the same dictionaries. The plugin is only listening - and **Tools →
Offline translate → Words you looked up** is where the switch, the threshold and
the list of what has been counted all live.

<img src="docs/screenshots/words-submenu.png" alt="A submenu titled Underline
them on the page, with a checkbox, an item reading Underline after: Every word
you look up, and three more: Words underlined now, Import from KOReader's lookup
history, and Clear looked-up words" width="380">

By default **every word you look up** is underlined: a word you had to look up is
a word you did not know, which is the whole of what a mark claims. **Underline
after** raises it to two lookups, or three, or five, if you would rather mark
only the words that keep defeating you - the effect is on the very next page, so
it is worth trying both ways. Nothing is lost either way: every lookup is counted
from the first, so raising the setting hides marks and lowering it brings them
back.

Tapping an underlined word opens the dictionary, exactly as holding it would.
The popup carries **Learned** when the word is one the plugin is marking, and
that takes its underline out of every book at once.

<img src="docs/screenshots/learned-in-dictionary.png" alt="A dictionary
definition of the word meanwhile over a page of an English novel, with the
buttons Add to vocabulary builder, Highlight, Wikipedia, Search, Close, and
Learned at the bottom" width="380">

That is KOReader's own dictionary popup, with one button added to it - which is
also why the vocabulary builder is still sitting there above ours. The plugin
listens for lookups; it does not intercept them.

On a new install there will be nothing underlined for a while, because nothing
has been counted yet. **Import from KOReader's lookup history** fixes that: KOReader
has been keeping a record of every dictionary lookup you have ever made, and
importing counts them all in. The words are read, never written, and they are
filed under the language you are set up to read now - so run it while that is
the language you have been reading.

A word of warning worth having in advance: the more words you mark, the more of
the page carries an underline, and the more often a tap meant for the next page
lands on one instead. If a page starts feeling crowded, raise the threshold.

### The same list, away from the page

**Tools → Offline translate → Remembered translations** shows what the plugin is
keeping for the language pair you are reading, in alphabetical order: one tap
for a translation, one more to drop it. Other pairs are a row away rather than
gone, so phrases from a book you have finished are still there to clear out.

<img src="docs/screenshots/remembered-list.png" alt="A list titled Remembered
translations, subtitled en to pl, with nine English phrases in alphabetical
order and a last row reading Show all language pairs, 9 more" width="380">

**Words underlined now**, in the same submenu as the rest of the word settings,
is the same idea for words: what is being marked in the language you are
reading, alphabetically, with the number of times each one caught you out.
Tapping a row offers the one thing there is to do about it.

### Taking the list somewhere else

**Tools → Offline translate → Export remembered translations** writes what is
remembered for the pair you are reading into a tab-separated file, in the same
directory KOReader's own exporter writes to:

```
koreader/clipboard/offlinetranslate-en-pl.tsv
```

Two columns, phrase and translation, which is what Anki imports into a
two-field note - no add-on, no conversion, nothing to set. The full path is in
the message that follows, because it is not somewhere you would guess.
Exporting again replaces the file rather than growing it: what you get is a copy
of what the plugin remembers now.

<img src="docs/screenshots/export.png" alt="The plugin's menu with a message
over it: Saved en to pl to, followed by the full path of the file, ending in
koreader/clipboard/offlinetranslate-en-pl.tsv" width="380">

Only the pair you are reading goes in, deliberately. A deck holding both
directions at once asks you the wrong question half the time; switch the pair
and export again for a second file.

### What it will not do

Matching is literal. "the old man" is not recognized in "the old men", and a
language that inflects heavily will hide more of these than English does. What
survives that are short fixed expressions - which is where a phrase translation
earns its keep in the first place. Underlining currently works in EPUB and other
reflowable formats, not in PDF.

## Requirements

[KOReader](https://github.com/koreader/koreader), and a translation server
answering on loopback. `127.0.0.1` is the device itself: the server is an app
running on the same reader, not a machine somewhere else, which is why the
plugin never asks to turn on Wi-Fi and why your text has nowhere to go.

### On an e-ink reader (Android)

Install [Translator](https://github.com/DavidVentura/offline-translator) by
David Ventura - it runs the Firefox translation models on the device and can
serve them over a local HTTP API:

1. Install it from
   [F-Droid](https://f-droid.org/packages/dev.davidv.translator).
2. Open it and download the language packs you need.
3. In its settings, under **Advanced**, turn on **"Enable LibreTranslate
   compatible HTTP server"**. It listens on `127.0.0.1:5000` and stays bound to
   loopback unless you tell it otherwise.
4. In KOReader: **Tools → Offline translate**, and set the two languages. The
   plugin already points at that address out of the box. If nothing answers
   there, it says so and says what to check; if the server has moved to another
   port, a failed call offers the one it finds instead.

**The server lasts as long as Translator's process does.** It runs as a
foreground service with a notification, so switching to KOReader or going back
to the home screen leaves it running. Two things stop it: restarting the reader,
and swiping Translator away in the recent-apps list, which kills the process and
takes the notification with it. If that notification is gone, so is the server.

Translator starts the server when its own process starts, and after a reboot
nothing starts that process on its own. So either open the app once after each
restart, or let the system do it: allow Translator to launch at startup in
whatever your device calls its auto-start settings, and, if your device is
aggressive about closing background apps, exempt it from battery optimisation
too.

Nothing breaks if you forget. The plugin says it cannot reach the server and
what to check, and opening the app is all it takes.

### On a desktop, for development

```bash
tools/libretranslate.sh
```

runs LibreTranslate in Docker on the same address and API.

### Other servers

Anything that speaks the LibreTranslate API will do - `POST /translate` and
`GET /languages` are all this plugin asks for. The address is a setting, and any
loopback address is fine.

## Compatibility

The plugin is pure Lua and uses only what KOReader already ships, so it runs
wherever KOReader does. What decides whether it is useful on a given device is
whether that device can answer on `127.0.0.1`.

| | |
| --- | --- |
| **Tested daily** | Onyx Boox Page - Android, e-ink - with Translator |
| **Tested in development** | KOReader desktop build on macOS, with LibreTranslate in Docker |
| **Should work, untested** | any Android e-ink reader that can run Translator |
| **Runs, but with nothing to talk to** | Kobo, Kindle, PocketBook and other non-Android readers, where no on-device translation server exists that we know of |

On a reader with no server of its own you can point the plugin at a machine on
your network, and it will work - but it asks you to confirm first, because at
that moment your text starts leaving the device, which is the one thing this
plugin exists to prevent. Nobody should end up there by accident.

Two more limits worth knowing, neither of them device-specific:

- **Underlines need a reflowable format.** EPUB, FB2, MOBI and the rest are
  marked; PDF is not. Translating a selection in a PDF uses a separate path for
  placing the bubble, which is written but has not been verified on a device.
- **Matching is literal.** "the old man" is not recognized in "the old men", so a
  heavily inflecting language hides more marks than English does. What survives
  that are short fixed expressions, which is where a phrase translation earns its
  keep anyway.

## Install

Download the zip from the
[latest release](https://github.com/fundacja-reborn/offlinetranslate-koplugin/releases/latest),
unpack it, and copy the `offlinetranslate.koplugin/` directory it contains into
the `plugins/` directory of your KOReader data directory. Restart KOReader.
Copying that directory straight out of a clone of this repository works just as
well. For development on macOS:

```bash
tools/install-dev.sh
```

This symlinks the plugin into `~/Library/Application Support/koreader/plugins/`,
so edits are picked up on the next restart.

## Configuration

Everything has a working default, and the plugin runs without a configuration
file. Settings live in KOReader's settings directory, so they survive plugin
updates, and are all edited from **Tools → Offline translate**: the language
pair, the address the server listens on, whether a dragged selection opens the
menu or translates right away, a connection test, and the translation
cache.

<img src="docs/screenshots/settings.png" alt="The plugin's settings: the two
languages, the server address, what a dragged selection does, a connection
test, whether translations are remembered, whether remembered phrases are
underlined, a submenu for words you looked up, the list of remembered
translations with a count, and an item that exports them" width="380">

The two language items list what the server itself reports it can do, asked
fresh each time they are opened. That is deliberate: language packs are
downloaded one at a time, so a list built into the plugin would offer languages
your device does not have, and the mistake would only show up later as a failed
translation. Download a pack in the translation app, reopen the item, and it is
there. Targets are narrowed to what the chosen source language can reach.

## Language

The plugin's own interface follows the language configured in KOReader, falling
back to English. Translations live in
`offlinetranslate.koplugin/offlinetranslate/l10n/`; adding a language is one
file, no build step.

## Why it works the way it does

[DECISIONS.md](DECISIONS.md) collects the decisions that shaped the code - what
each one was weighed against and what it costs. Worth reading before changing
anything that looks arbitrary.

## Development

```bash
tools/test.sh                             # run the test suite
tools/lint.sh                             # luacheck and shellcheck, as CI runs them
tools/check-i18n.sh                       # translation catalogs vs. strings in code
tools/check-namespace.sh                  # local modules are required with their prefix
tools/package.sh                          # build a distributable zip
```

Together those four are exactly what CI runs, so a green run here is a green run
there. `tools/lint.sh` uses whichever linter is installed and otherwise falls
back to the same containers CI uses, which is worth knowing on a machine where
neither is available natively.

The tests in `test/` load the plugin's own modules against stubs of the KOReader
API, with no test framework and no dependencies - any Lua interpreter runs them
in about a second. They cover what cannot be checked by using the plugin: how a
server's answer becomes an error message, where a bubble is placed, which
selections the plugin claims, which languages a picker offers, and how it looks
for a server. Anything a reader can see is verified by hand instead.

## Who makes this

[Reborn Foundation](https://reborn.org.pl), a non-profit in Poland. This plugin
came out of the same conviction as the rest of our work: software should not
have to see your data in order to be useful to you. Here that means a
translation engine on your own device; elsewhere it means encryption you hold
the keys to.

The other thing we build is [**re/apps**](https://reapps.eu) - two offline-first
web apps under the same AGPL licence:

- **[re/notes](https://reapps.eu/notes)** - notes and documents, in Markdown
- **[re/task](https://reapps.eu/task)** - tasks, subtasks and reminders

Both are end-to-end encrypted with a zero-knowledge design: everything is
encrypted on your device before it reaches the server, which holds ciphertext
and can read none of it - not your notes, not your tasks, not the metadata.
Free to use, no email required, hosted in the EU, no tracking and no ads. And
[open source](https://github.com/fundacja-reborn/reapps), so you can host it
yourself rather than take our word for any of the above.

## License

Copyright (C) 2026 Fundacja Reborn

This program is free software: you can redistribute it and/or modify it under the
terms of the GNU Affero General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version. It is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY. See [LICENSE](LICENSE) for the full text.

AGPL-3.0-or-later is KOReader's own license, which is what a plugin loaded into
its process has to be.
