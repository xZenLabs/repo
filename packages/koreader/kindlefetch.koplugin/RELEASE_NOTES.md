# v0.5 · 2026-10-05

KindleFetch no longer holds KOReader up while it searches: pages arrive several times faster, compressed, and a tap cancels a search. Downloads ask before replacing a book, go to a `.part` file until they finish, and download completely in the background so they can be found again from the new Downloads menu entry. Load more stays where you were, settings change without flashing the screen and can clear the cache, errors stay on screen until dismissed, and you're told when every result was in a language or file type you haven't chosen. Plus speed-ups and fixes throughout.

**How much faster?** Library Genesis now sends each page of results compressed, about 29 kB where it used to send 267 kB. A page that takes 13–29 seconds to arrive in v0.4 now takes 3–6 seconds (about 4x faster!). A search reads up to 5 pages, so one that used to freeze KOReader for over a minute now finishes in well under half that, and KOReader stays usable the whole time.

Changes since v0.4:

- Read the settings file once, and only write it when a setting changes (10095d6)
- Read each cache once, save covers together, and keep at most 100 searches (e6189a9)
- Give up on a site that doesn't answer after 10 seconds, rather than a minute (c9bcc0e)
- Check for updates in the background, once a day, without repeating offers that were turned down (a61eb7d)
- Read a book's size from its download, rather than asking for it first (2757f21)
- Refresh only the part of the screen that changed, without flashing it (3b78a60)
- Fix Read now crashing once the book the download was started from has closed (06b6eb0)
- Ask before downloading over a book that's already there (870d853)
- Download books to a .part file, and give up on downloads that stall (d11bee4)
- Remove the files of covers dropped from the cache, and of downloads KOReader closed during (30ef2ed)
- Show titles as they're written, shortened to fit the screen rather than to 50 bytes (c26b3ef)
- Don't let a mirror add options to curl, and search without Wikipedia's list of mirrors (2bfc030)
- Say when a download fails because curl isn't installed (acb78a9)
- Say when Library Genesis is too busy to send a book (ebef7c3)
- Fetch pages with curl where it's up to it, compressed (e14f4c3)
- Search without holding KOReader up, and let a tap call the search off (ac2d717)
- Get the next page's covers ahead, and give up on covers that stall (9da141b)
- Search when enter is pressed on the keyboard (c38cefe)
- Show what went wrong in a message that stays until it's dismissed (4231522)
- Add more books to the list where Load more was tapped, rather than going back to its first page (0ecc773)
- Say when books were found, but none in the languages and file types chosen (1feb0a3)
- List the downloads in progress in the menu, to show a hidden one again (0504a17)
- Change settings in the menu that's open, on the page it's on, and add a way to clear the cache (fb78a6a)
- Say above the books what was searched for, and how many were found (6d510f8)
- Check that cancelling a download leaves nothing of it behind in the end-to-end tests (8553b5a)
- Say when Library Genesis' servers fail to send a book, and which HTTP error stopped a download (68dd06f)
- Fix the edge of KOReader's menu showing in the corners of the settings (3c0218d)
- Put the comment on searching above the function it describes (d8e34d2)
- Update README screenshots (e7576ad)
- Show README screenshots side by side (f06ac89)

# v0.4 · 2026-09-30

KindleFetch now searches Library Genesis, as Anna's Archive blocks the plugin. Covers load in the background and can be tapped to see them full size, finished downloads can be opened straight away, Wi-Fi turns on when needed, and update checks can be turned off. Plus many fixes.

Changes since v0.3:

- Update TODO.md (a66aa76)
- Fix null value (10b4389)
- Update TODO.md (cf591de)
- Add stricter timeouts for book cover downloads (2a7d72e)
- Skip curl version check if running in android (3f66323)
- Add notification for multiple download error message (7c3f674)
- Fix string concat (a80cf35)
- Extend download timeout (d2eafe5)
- Delete TODO.md (1c96744)
- Update koreader (777f6af)
- Move TODOs into issues (f4bfdf7)
- If wifi is off on search, prompt user and ask if they want to connect to wifi Fixes william-spongberg/KindleFetch.koplugin#5 (00ed94c)
- Do not check for updates if wifi is not connected Fixes william-spongberg/KindleFetch.koplugin#15 (9b4185f)
- Update koreader (1ca4a07)
- Fix installed version detection and updates on android Fixes william-spongberg/KindleFetch.koplugin#2 (64e45ba)
- Add tests (b6a601e)
- Run tests on push (a65f222)
- Add release workflow (bb01a93)
- Fix proxy not being used for curl downloads (26838f8)
- Fix next mirror being skipped after a mirror fails (c89fb9c)
- Return search results after looking up new mirrors (e17c5df)
- Do not cache empty search results (83bcb10)
- Trim book type after removing emojis (7a7d41d)
- Fix download failing twice when looking up new mirrors (0b88678)
- Show a clear error when a download is empty (6c383ef)
- Fix crash when showing covers dropped from the cover cache (48a99fb)
- Show a message when there are no more books to load (34b0026)
- Remount root as read-only when the curl backup fails (a1aecbf)
- Add tests for the rest of the plugin (9be45b5)
- Report test coverage in CI (8a5d60f)
- Fix crash when showing a hidden download again (9e8abc8)
- Remove deprecated name from plugin metadata (7fed739)
- Show covers in every open search result once they download (c732456)
- Send a referer with downloads so book covers are not empty (21e611f)
- Show full-size covers when enlarging them in the download prompt (d4e46f1)
- Keep the covers that downloaded when others fail or stall (2681a93)
- Read more pages of results so searches show enough books (16b6998)
- Update README screenshots (4539732)
- Stop stalled covers from holding up the download prompt (43314b2)
- Show each book once in search results (056d168)
- Update README screenshots (b493022)
- Keep the files of downloads started in the same second apart (794b705)
- Show the progress again when choosing a book that is already downloading Fixes william-spongberg/KindleFetch.koplugin#20 (b6c6c58)
- Fix downloads failing when curl finishes between checks (28e7e4b)
- Check the search dialog is on screen in the gesture end-to-end test (c388cc1)
- Remove the Russian fiction book type (8f22c13)
- Update search results screenshot (6f58735)
- Search Library Genesis instead of Anna's Archive Fixes william-spongberg/KindleFetch.koplugin#24 (c073e95)
- Clear cached searches and mirrors after updating Fixes william-spongberg/KindleFetch.koplugin#23 (6d8cf44)
- Make automatic update checks optional and quiet Fixes william-spongberg/KindleFetch.koplugin#25 (8197710)
- Open search when the gesture action is used Fixes william-spongberg/KindleFetch.koplugin#4 (8ebeee0)
- Show book details in black so they are easier to read Fixes william-spongberg/KindleFetch.koplugin#3 (5ca5f18)
- Turn on wifi and search once connected Fixes william-spongberg/KindleFetch.koplugin#1 (1d01781)
- Time out stalled requests in tests like luasocket does (85ec600)
- Cancel downloads when KOReader exits Fixes william-spongberg/KindleFetch.koplugin#19 (04fb372)
- Offer to open books once they have downloaded Fixes william-spongberg/KindleFetch.koplugin#10 (b88f44a)
- Make cache expiries configurable in settings Fixes william-spongberg/KindleFetch.koplugin#12 (002faa7)
- Retry book cover downloads through the proxy Fixes william-spongberg/KindleFetch.koplugin#14 (9444373)
- Download book covers in the background Fixes william-spongberg/KindleFetch.koplugin#18 (8cb5e72)
- Add development guide for running KindleFetch on Linux Fixes william-spongberg/KindleFetch.koplugin#13 (488a79f)
- Add end-to-end tests that run in a real KOReader (f3e0c41)
- Fix download progress showing a total size of 0.0 MB (5cd0241)
- Search for Harry Potter and the Chamber of Secrets in end-to-end tests (749ff7d)
- Show placeholders while book covers download (351e199)
- Hide downloaded covers in search results when book covers are turned off (daa4619)
- Show the book title in bold in the Read now prompt (9de87a4)
- Only load the repository's copy of KindleFetch in the end-to-end tests (d29e49d)
- Make the download prompt easier to read (ecc380b)
- Update download prompt screenshot (97827b8)
- Centre the Read now prompt (293ba7f)
- Update README (42743e9)
- Say a download was cancelled rather than that it failed (1bc686b)
- Log the rows of search results that aren't books as debug (61b5d78)
- Check whether downloads are running without starting a shell (d7be51f)
- Update Read now screenshot (d8b5b0a)
- Log enough detail to debug a crash.log from a device (208c94c)
- Say when mirrors are being looked up on Wikipedia (86e25f1)
- Say when the full-size cover is loading (3d71fa8)
- Close the search box when opening a downloaded book (e81130f)
- Handle being offline when downloading, loading more and looking up mirrors (a60a5e2)
- Find the titles of comic issues that the search results leave out (f328ee2)
- Default to every kind of book in English, and only offer file types KOReader opens (32f54a8)
- Say when every language, file type or book type is turned off (c879d91)
- Keep saying the full-size cover is loading until it arrives (2f5f184)
- Start each end-to-end test with empty caches, and test falling back to other mirrors (ae72169)
- Update README for the new default preferences (ced751e)
- Update settings screenshots (a9e4925)
- Format with StyLua (3469e36)
- Fix luacheck warnings (08c0f3f)
- Check formatting and lint in CI (49e7699)
- Leave the Lua that CI installs out of linting (da19045)

# v0.3 · 2026-07-19

UX upgrades all around thanks to community feedback

- **Automatic plugin updating**: checks latest release version on Github, and prompts the user for an update with patch note information (suggested by [kelmi3D](https://www.reddit.com/user/kelmi3D/))
- **Show book covers in search**: optionally show book covers alongside books in search results. Better formatted book information using a custom menu (suggested by [2211mg](https://www.reddit.com/user/2211mg/)). Note that book cover downloads can be hit or miss on older Kindles so there is a toggle for it in settings.
- **Tap book cover to expand to full screen** (suggested by [IbnRami](https://www.reddit.com/user/IbnRami/))
- **Simplify download prompt**: only have path + download buttons, and tap outside to close (suggested by [IbnRami](https://www.reddit.com/user/IbnRami/))
- **Extend search caches**: search caches now expire after 2 weeks and have max 1000 entries
- **Prompt updates**: plugin and curl updates will prompt the user first rather than being triggered automatically

# v0.2 · 2026-07-12

Big update this one

- **Caching**: Caches search results (72 hours), mirror URLs (7 days), and book covers (for length of search) to minimise network requests and improve performance
- **Preferences**: Filter results by preferred languages, file types, and book types
- **Book Cover Previews**: Display cover images in download previews
- **Background Downloads**: Downloads run in the background using curl, with non-blocking UI updates
- **Automatic Curl Updates**: Ensures a compatible curl version (8.17.0+) is available
- **Automatic Retry Logic**: Fallback to other available urls if connection fails
- **Safe File Handling**: Automatic filename sanitisation and directory management

# v0.1 · 2026-07-06

**Initial release** - it works, but don't expect much else. And don't expect it to always work.
