# Bookshelf description search

A KOReader userpatch that finds a book's description (the blurb) online and
uses it in place of the one embedded in the file, the same way the
[Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin) plugin's Cover tab
does for covers.

## What it does

- Searches **Apple Books** and **Google Books**: first by ISBN, then by title
  and author.
- Lets you browse the candidates, **edit** one if you like, and save your pick.
- Cleans every description the same way, keeping only paragraphs and
  italics, so blurbs look consistent across your library.
- Saves the result as KOReader's custom description
  (`book.sdr/custom_metadata.lua`), the same field you can edit by hand in
  *Book information*. **The ebook file is never modified.**
- **Restore original description** removes your custom one and brings back the
  file's own.

Searches use the book's language: an Italian book is looked up in the Italian
Apple Books store and in Italian on Google Books. If nothing turns up, the US
store is tried as a fallback.

## Install

1. Download `2-bookshelf-description-search.lua` from the
   [latest release](../../releases).
2. Copy it to the `patches` folder inside your KOReader folder. On Kobo that
   is `/mnt/onboard/.adds/koreader/patches/` (create `patches` if it does not
   exist; `.adds` is a hidden folder).
3. Restart KOReader.

Bookshelf is optional: without it the patch still works from KOReader's file
browser.

## Use

**In Bookshelf**, open a book's popup and go to the **Blurb** tab, right after
*Cover*:

- **Search online…** looks the book up. Use the arrows to flip through the
  results; the counter shows which one you are on and where it comes from
  (marked *ISBN* when it matched the exact edition).
- **Use this** saves the description you are looking at.
- The **pencil** opens the description in an editor before saving.
- The **restore** icon appears once a custom description is set.

**In the file browser**, long-press a book and pick **Search description
online** (or **Restore original description**).

The interface is in English, or in Italian when KOReader is set to Italian.

## Settings

A few options sit at the top of the file, in the `CONFIG` table:

| Option | Default | What it does |
| --- | --- | --- |
| `apple_country` | `nil` | Apple Books store (e.g. `"it"`). `nil` = from the book's language, else KOReader's |
| `google_lang` | `nil` | Google Books language. `nil` = same logic as above |
| `apple_fallback` | `"us"` | Store tried when nothing is found. `nil` = off |
| `max_per_source` | `5` | Results kept from each source |
| `keep_italics` | `true` | Keep italics (blurbs often use them for titles) |
| `bookshelf_tab` | `true` | `false` = a card in Bookshelf's Actions instead of a tab |

## Good to know

- The search needs Wi-Fi. KOReader asks to turn it on if it is off.
- The Blurb tab hooks into internal Bookshelf modules. If a Bookshelf update
  renames them, the tab simply disappears and the action shows up in the
  long-press menu instead: no errors.
- Descriptions belong to their publishers and stores. The patch only copies
  them into your own device's metadata, for your personal use.
- If you remove the patch, saved descriptions stay: they are ordinary
  KOReader metadata.

## License

[AGPL-3.0](LICENSE), the same licence as KOReader and Bookshelf.
