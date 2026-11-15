This is a user patch for KOReader made with ChatGPT Codex. It changes the appearance of books in the Bookshelf plugin for more realistic depictions of book length and progress, and adds spines that include customizable book details.


<img width="356" height="481" alt="Cover View small_2026-11-06_113711" src="https://github.com/user-attachments/assets/c1beddd5-0bed-4ca1-86ad-6da19897de08" /> <img width="356" height="481" alt="Spine View large_Screenshot_2026-11-06_144414" src="https://github.com/user-attachments/assets/81372ff9-31de-4df9-96a4-12bb9553caea" />

<img width="356" height="481" alt="Cover_view_large__2026-11-11_212200" src="https://github.com/user-attachments/assets/63d449d5-9212-44b1-a4cf-337c2c54f1b4" /> <img width="356" height="481" alt="Covers_critters_2026-11-11_221629" src="https://github.com/user-attachments/assets/308f7914-6fda-4f68-ac47-7543d8ce0d54" />

# Progress Bookmarks for KOReader Bookshelf

## Features

- Adds reading-progress bookmarks to Bookshelf’s Cover View and face-out Spine View.
- Tracks progress vertically, horizontally, or both, with controls for bookmark visibility, position, length, thickness, colour, and detail.
- Adds adjustable page-line count and binding/spine rendering options.
- Customizes spine text, including title, author, and series index display, font, size, colour, and overflow options.
- Includes separate Cover View and Spine View settings, with independent enable toggles and default-reset options.
- V1.1 brings image-based bookmarks with selectable bookmark material and charm, plus critters that climb them when certain conditions are met (user-definable).
- Long-pressing on a book allows you to set a custom bookmark or critter for that book regardless of global settings.
- Readme files in bookmark_images folder show how users can create their own bookmark and critter images and install to custom folders.
- Includes a GitHub update checker that can install the latest stable release after confirmation, while saving a backup.

## Installation

Download `2-bookshelf-progress-bookmark.lua` from the **Releases** section of this repository and copy it into:

`koreader/patches/`

Download `bookmark_images` directory from the **Releases** section of this repository and copy it into:

`koreader/`

Restart KOReader to apply the patch.

## About

Progress Bookmarks draws a physical-book-inspired overlay on book covers in Bookshelf, complete with a spine displaying book information and a page stack that reflects the book's length.

Instead of a traditional progress bar, Progress Bookmarks uses a bookmark that sits vertically within the pages, just like a real bookmark. It also moves horizontally, retaining the familiar visual indication of reading progress and making it easy to see how far along you are in shorter books.

The bookmark's length, thickness, and colour are adjustable.

The spine is created by copying a section of the cover, giving each book a binding that feels connected to its original artwork. Spine thickness, text font, and colour are customizable.

Cover View and Spine View can be configured independently. Spine View also includes options for customizing the text on Spine Only books, allowing you to use your preferred spine font whether or not you enable the bookmark functionality.

## Spine

Give your books a distinctive, physical-book look with customizable bindings and spine text.

- **Adjustable binding widths** — Choose Thin, Medium, or Thick bindings, with separate controls for Cover View and Spine View.
- **Custom spine text** — Display the book's title, author, and series index.
- **Text customization** — Adjust text size, colour, and font matching.
- **Flexible title layout** — Choose between truncating long titles or allowing them to wrap onto a second line.
- **Series indices** — Multi-digit series numbers follow the spine's orientation, while single-digit indices sit neatly at the foot.
- **Page stack customization** — Adjust how many pages appear on each line, with up to six lines of page detail.

## Bookmark

Keep track of your reading with a customizable progress bookmark.

- **Flexible tracking** — Follow your progress vertically, horizontally, or in both directions.
- **Adjustable thickness** — Choose Thin, Medium, or Thick, with independent settings for each view.
- **Custom lengths** — Configure bookmark length presets to suit your preferred appearance.
- **Style options** — Customize the bookmark's colour, pattern, charm and critter
- **Bookmark details** — Toggle additional visual details on or off.
- **View-specific settings** — Cover View and Spine View can each have their own bookmark behaviour and appearance.

## Recommended Settings

Progress bookmarks seems to work best with the following Bookshelf settings:

- Disable the icons for Favourites and Reading Bookmark.
- Disable the Spine Mode drop shadow.
- Use square corners.
- Use Hardcover style.

My setup might also involve other settings I've forgotten, so your mileage may vary. Let me know if anything looks weird!

## Development

I started working on this idea in the Spring, editing other people's code line-by-line with ChatGPT and having to manually update several plugin files every time there was an update.

This Fall, I was given a (still very old) computer that could actually run Codex. With a little help from AI, I was finally able to turn the idea into a proper patch, so I'm sharing it in case anyone else is interested.

I currently use Bookshelf exclusively, so BookCraft is Bookshelf-only for now. I can share the old Project:Title patch, and could probably port it to SimpleUI and ZenOS if there's interest.

Everything is open-source, so feel free to experiment, modify, and make it your own!

## Acknowledgements

I originally made this for **Project:Title**, which I really loved for its idea of progress bars that vary in size depending on the length of the book.

[Project:Title by u/joshua-cant](https://github.com/joshuacant/ProjectTitle)

This patch was originally inspired by the **RealBooks** patch by u/ReaLx3m, which made realistic visual page counts a reality and got me thinking about bringing progress bars into the same visual language.

[RealBooks for KOReader](https://github.com/ReaLx3m/KOReader-AI-Slop-User-Patches/tree/main)

**Bookshelf**, by u/AndyHazz, is my current favourite KOReader UI. It really brings the physical-book feeling home: I can skim through my library, peek at the backs of books, and now even sort them into box sets.

[Bookshelf](https://github.com/AndyHazz/bookshelf.koplugin)

Thank you to these developers, and to all the developers of KOReader. KOReader has helped me read more and has been a lot of fun to work with.


I just made this for myself and I've never uploaded anything to Github before so please let me know if you have any requests or suggestions.



## Updating

Use **Check for updates** in Progress Bookmarks Patch Settings to check the latest stable GitHub release. The updater installs only after confirmation, verifies the release version, patch filename, and Lua syntax, saves a versioned backup beside the patch, and asks you to restart KOReader.
