# The Booksheet

**The Booksheet** is a one-page newspaper of book news, made up of the sections and sources that you choose.

<img src="images/booksheet.png" width="536" alt="The Booksheet: four book sections above a list of book news">

- Pick **four sections**: any mix of bestseller lists by genre, or see what's **Just out**, or **Reviewed this week**.
- Page through the **top 10** in each section with **More** and **Back**.
- Read **Book news** headlines from the sources you turn on.
- Tap any book or headline for details, add a book to a **Want to read** list, or get a **QR code** to open it on your phone at your favorite online store.

## Tested on

Developed and tested on a **Kobo Clara BW**.

Reports from other devices are welcome.

## Install or update

1. Download `booksheet.koplugin.zip` from the [Releases](../../releases) page and unzip it. You should have a folder named `booksheet.koplugin`.
2. Connect your e-reader to a computer with USB.
3. Copy into or replace the `booksheet.koplugin` folder in KOReader's `plugins` folder. On a Kobo that is `.adds/koreader/plugins/`. The `.adds` folder is hidden: on a Mac, press **Cmd+Shift+.** in Finder to show it.
4. Eject the device and restart KOReader.

To uninstall, delete the folder.

## Using it

Open it from the top menu → Tools tab (wrench icon) → **The Booksheet**. You can also assign it to a gesture in KOReader's gesture settings.

### The page

It should be pretty self-explanatory. But just in case:

- **More** and **Back** page through a single section.
- Tap a **book** to see its details, get a QR code, or save it to Want to read.
- Tap a **headline** to see its source, and get a QR code to the article. When the feed includes the article's text, you can also read it right on your e-reader.
- Tap **Updated** in the bottom-left corner to update now.
- Tap **Want to read** at the bottom to see the books you saved. They stay on your list after they leave the page.

| Tapping a book | Tapping a headline |
|:---:|:---:|
| ![A pop-up for The Calamity Club with its cover, author, list rank, description, and buttons for Want to read and QR Code to Book](images/book.png) | ![A pop-up for a Lit Hub article with its source, date, opening text, and buttons for Read article and QR Code to Article](images/article.png) |

### Book news

Book news shows the 20 newest stories from the past 7 days across the sources you turn on in Settings, newest first.

### Settings

Tap **Settings** in the bottom-right corner:

- **Your sections**: choose what goes in each of the four spots.
- **Book covers**: show or hide the cover on the #1 book of each bestseller list.
- **Text size**: small, medium or large.
- **News sources**: The New York Times, NPR Books, Lit Hub, Book Riot, Locus, Reactor and The eBook Reader. (If you have a favorite book-news source with an RSS feed and you think it should be here, let me know!)
- **Want to read**: your saved books.
- **Book QR codes open at**: Bookshop.org, Kobo, Amazon, Apple Books, Libby or WorldCat. For Libby, you can enter your library so the code opens a search there.
- **Update automatically**: on open, once a day, or manually. "On open" doesn't actually update if the most recent update was less than an hour ago.

| Settings | Choosing a section |
|:---:|:---:|
| ![The Settings page, with groups for your sections, your page, your books and updates](images/settings.png) | ![The section chooser, with Just out and Reviewed this week above the bestseller lists from Apple Books](images/sections.png) |

## Where the information comes from

- **Bestseller lists** and **Just out**: Apple Books.
- **Reviewed this week**: The New York Times.
- **Book news**: the public RSS feeds of the sources you turn on.

The Booksheet needs Wi-Fi to update. It doesn't use an account. Everything stays on your device.

The Booksheet isn't affiliated with or endorsed by any of these sources or stores.

## Credits

Written by David Friedman, working with [Claude](https://claude.com/claude-code).

## License

[AGPL-3.0](LICENSE), the same license as KOReader.
