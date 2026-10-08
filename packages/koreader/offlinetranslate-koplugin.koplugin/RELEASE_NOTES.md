# v0.6.0 · 2026-08-08

The plugin now does what it is for without being asked first. Four defaults change, and every one of them is still a switch in **Tools → Offline translate**.

> **Upgrading from 0.5.x changes what selecting text does, and what a page looks like.** If you left these switches alone, dragging out a selection will translate it, and underlines will start appearing once you restart. Nothing that has been counted or remembered is touched, and each default is one tap from off.

| | 0.5.x | 0.6.0 |
| --- | --- | --- |
| a dragged selection | opens the selection menu | **translates as you let go** |
| remembered phrases | not underlined | **underlined** |
| words you look up | not underlined | **underlined** |
| lookups before a word is marked | 2 | **1** |

## Straight to the translation

Let go of a selection and the translation is there, in a bubble over the sentence it came from, with no menu in between. Until now that was a setting you had to find.

**Nothing is taken away by it.** Every translation carries a **Selection menu** button, so highlighting, copying or a note is one tap from the bubble. And everything this mode declines opens the menu KOReader would have opened: a highlight you tapped, a selection with no word in it, one past the length limit, and a translation that failed - so a fresh install with no server running ends its first drag on a message naming the missing step and then the menu, not on a dead end.

**One thing has not changed.** If KOReader's own **Long-press on text** (Settings → Taps and gestures) is set to anything other than "Ask with popup dialog", that setting still wins and this one does nothing. You chose it on purpose.

## Marks from the first time

A phrase you translate is underlined wherever it turns up again, and so is a word you look up in a dictionary - both out of the box now, and a word from the first lookup rather than the second. A word you had to look up is a word you did not know, which is the whole of what a mark claims. **Underline after** still raises it to two, three or five if you would rather mark only the words that keep defeating you.

The argument that kept these off was that changing what a page looks like is a regression for a reader who never asked for it. That was aimed at the wrong reader: the one who never wanted a changed page is the one who never installed a translation plugin.

Dictionary lookups are therefore counted from the moment the plugin is installed. That record stays on the device, like everything else here, and KOReader has been keeping a lookup history of its own all along - it is the same one **Import from KOReader's lookup history** reads.

## Install

Download `offlinetranslate.koplugin-0.6.0.zip` below, unpack it, and copy the `offlinetranslate.koplugin/` directory into the `plugins/` directory of your KOReader data directory. On Android that is `/sdcard/koreader/plugins/`. Restart KOReader - plugins are loaded once, at startup.

Upgrading is the same copy over the top. Settings and remembered translations live in KOReader's settings directory and are left alone.

## Requirements unchanged

KOReader, and a translation server answering on loopback - the plugin never asks to turn on Wi-Fi and only ever talks to `127.0.0.1`. See the [README](https://github.com/fundacja-reborn/offlinetranslate-koplugin#readme) for [Translator](https://f-droid.org/packages/dev.davidv.translator) on Android, or LibreTranslate on a desktop.

The short version of every release so far is in the [CHANGELOG](https://github.com/fundacja-reborn/offlinetranslate-koplugin/blob/main/CHANGELOG.md).

# v0.5.0 · 2026-08-08

The gesture decides what gets translated now, and the dotted underlines find the punctuation books are actually printed with.

A 0.4.x install upgrades in place - nothing moves in the settings file, in what is remembered, or in the HTTP contract.

There is also a **[CHANGELOG](https://github.com/fundacja-reborn/offlinetranslate-koplugin/blob/main/CHANGELOG.md)** in the repository from this release on: every version so far, short enough to read in one sitting. These pages keep the longer story.

## What you drag is what gets translated

**A selection you drag out is translated whatever its length.** Dragging over a single word used to end in the selection menu and nothing else: the plugin turned single words down on the grounds that dictionaries are better at them, and KOReader does not count a dragged word as a word selection either, so nothing picked it up.

The gesture decides now. **A long press still goes straight to the dictionaries** and never reaches this plugin, so nothing is taken away from them - and a drag is somebody asking for the thing they dragged over.

That came out of two reports on the same morning: first "self-efficacy is not translated", then, after a rule about hyphens written to answer it, "Todd's is not translated". The second one behaved exactly as decided, which is what made it the useful report. Whatever a word-counting rule says on a given day, it is answering a question the reader has already answered with the gesture.

## Fixed

**Punctuation as books actually print it no longer hides a phrase.** A remembered phrase standing behind a curly quotation mark, a guillemet, a dash or a non-breaking space was never underlined, because Lua's idea of punctuation covers ASCII and nothing else. For the same reason a word the plugin had to split in two - "self-efficacy" - never reached the underlining threshold however often you looked it up.

**A word you look up is underlined everywhere it stands on the page**, at the moment it crosses the threshold rather than after the next page turn - which read as the plugin changing its mind about the other occurrences. "Learned" now takes away every one of its underlines too, instead of leaving the second one on screen.

**A word broken across a line end** was underlined by a single line running margin to margin under the lower half of it. Both halves are underlined now, each under itself.

**A phrase you highlight yourself stops being marked.** With "translate right away" on, the only route to a plain highlight runs through the bubble, so such a phrase ended up carrying a grey highlight and a dotted underline at once - and the underline could not be tapped, because a tap on KOReader's own highlight is handed back to KOReader untouched. The dots stop where a highlight sits, line by line, so a highlight covering one line of a phrase leaves the other line marked and still tappable.

Take the highlight away and the mark comes back. Highlighting says "this passage matters", not "I know this phrase" - and readers highlight sentences precisely because those were the hard ones. **A translation that comes back from memory now carries "Learned" whichever door you opened it through**, which for a phrase you had also highlighted used to mean four dialogs ending in a bubble with no button on it.

## Install

Download `offlinetranslate.koplugin-0.5.0.zip` below, unpack it, and copy the `offlinetranslate.koplugin/` directory into the `plugins/` directory of your KOReader data directory. On Android that is `/sdcard/koreader/plugins/`. Restart KOReader - plugins are loaded once, at startup.

Upgrading is the same copy over the top. Settings and remembered translations live in KOReader's settings directory and are left alone.

The *Source code* archives GitHub generates below hold the whole repository - tests, tooling, screenshots - and are not directly installable.

## Requirements unchanged

KOReader, and a translation server answering on loopback - the plugin never asks to turn on Wi-Fi and only ever talks to `127.0.0.1`. See the [README](https://github.com/fundacja-reborn/offlinetranslate-koplugin#readme) for [Translator](https://f-droid.org/packages/dev.davidv.translator) on Android, or LibreTranslate on a desktop.

# v0.4.1 · 2026-08-07

Patch release: one bug fixed, nothing added. A 0.4.0 install upgrades in place - no change to settings, to what is remembered, or to the HTTP contract.

## Fixed

**A translated selection could take over every tap in the book** ([#40](https://github.com/fundacja-reborn/offlinetranslate-koplugin/pull/40)).

After closing a translation bubble, the selection sometimes stayed on the page. From then on every tap - on another phrase, on a word, on empty space, even after turning the page - brought that same bubble back instead of turning the page or opening the mark under your finger. It cleared only by closing and reopening the book.

KOReader keeps a selection alive until something explicitly clears it, and while it is alive it reads every tap as one ending a long press. With "translate right away" that led straight back into the plugin, which found the phrase in its cache and showed the bubble again. The plugin now hands the selection back on every way out of a translation, including the ones that previously had no answer for it: a cancelled "Translating…", a cancelled search for a server, a selection past the length limit, and a server error reached from the selection menu.

One difference worth knowing: **cancelling the wait now clears the selection and does not open the selection menu**, while a server *error* still leads to that menu. A tap that says "stop" gets you the page back; an error is not your doing, so the words you selected are kept.

## Install

Unpack `offlinetranslate.koplugin-0.4.1.zip` into KOReader's `plugins/` directory, replacing the old `offlinetranslate.koplugin` folder. Settings and remembered translations live outside the plugin directory and survive the upgrade.

# v0.4.0 · 2026-08-07

Single words are underlined too now, on the same terms as translated phrases: look one up in a dictionary twice and it gets the same faint dotted underline wherever it turns up again, in every book.

<img src="https://raw.githubusercontent.com/fundacja-reborn/offlinetranslate-koplugin/v0.4.0/docs/screenshots/marked-words.png" alt="A page of Three Men in a Boat on an e-ink screen with seven faint dotted underlines" width="380">

## Words you looked up

The plugin still never translates a single word - those belong to the dictionaries, which are better at them than any translation model. Marking one needs no translation, only the knowledge that you looked it up, and KOReader broadcasts that.

Nothing in the dictionary path is wrapped or overridden: the same long press, the same popup, the same dictionaries, and the vocabulary builder still gets its words. Tapping an underlined word opens that popup, which carries **Learned** to drop the word from every book at once.

**Two lookups is the default, not a rule.** One lookup is curiosity; two means the word already got past you once. **Underline after** moves it to every lookup, or three, or five, and the effect shows on the next page. Every lookup is counted from the first whatever the setting says, so raising it hides marks and lowering it brings them straight back - nothing is thrown away either way.

**Import from KOReader's lookup history** counts in every dictionary lookup you have ever made, so the feature is not blank on the day you switch it on. Read, never written.

Off until asked for, like everything else here - and while it is off, the plugin does not count what you look up at all.

## Also

- The dotted underline is easier to see. The dots were thinner than they were wide with two dots of air between them, which on a 300 dpi panel came out as something you had to go looking for. They are square now, with one dot of air.

## Install

Unzip into KOReader's `plugins/` directory so you get `plugins/offlinetranslate.koplugin/`, and restart KOReader. Needs a translation server on `127.0.0.1` - see the [README](https://github.com/fundacja-reborn/offlinetranslate-koplugin#readme).

Still below one. The plugin sits on somebody else's API on both sides - KOReader's and the translation server's - and has to keep working across releases of each.

# v0.3.0 · 2026-08-06

Take the phrases somewhere else.

The plugin remembers what it has translated, so that meeting a phrase again
costs no waiting. That collection is also a record of what you kept having to
look up - and a record is worth having where you revise, not only where you
read.

## What is new

**Tools → Offline translate → Export remembered translations** writes what is
remembered for the language pair you are reading into a tab-separated file, in
the same directory KOReader's own exporter writes to:

```
koreader/clipboard/offlinetranslate-en-pl.tsv
```

Two columns, phrase and translation, which is what **Anki** imports into a
two-field note - no add-on, no conversion, no separator to choose. The message
that follows gives the full path, because it is not somewhere you would guess.

Exporting again replaces the file rather than growing it: what you get is a copy
of what the plugin remembers now. Only the pair you are reading goes in, and
that is deliberate - a deck holding both directions at once asks you the wrong
question half the time. Switch the pair and export again for a second file.

Nothing leaves the device. The file is written on the reader, and what becomes
of it after that is yours to decide.

## Install

Download `offlinetranslate.koplugin-0.3.0.zip` below, unpack it, and copy the
`offlinetranslate.koplugin/` directory into the `plugins/` directory of your
KOReader data directory. On Android that is `/sdcard/koreader/plugins/`.
Restart KOReader - plugins are loaded once, at startup.

Upgrading from 0.2.x is the same copy over the top. Settings and remembered
translations live in KOReader's settings directory and are left alone.

## Requirements unchanged

KOReader, and a translation server answering on loopback - the plugin never asks
to turn on Wi-Fi and only ever talks to `127.0.0.1`. See the README for
[Translator](https://github.com/DavidVentura/offline-translator) on Android, or
LibreTranslate on a desktop.
