# v0.25.0 · 2026-11-21

# KOAssistant v0.25.0 Release Notes

Answers now arrive in Markdown (bold, headings, lists) while they stream, and stay on their first page so you can read from the top. The minimal popup shows its answer the way the chat window does, and Arabic, Hebrew, Devanagari and emoji get proper fonts. X-Rays can match a name by its capitals alone, end with a Conclusion at the end of the book and say what each way to build gives; AI merge between books is experimental for now. There are new models, Amazon Bedrock as a provider, and many fixes, among them a rare crash after background work and a freeze when the screen turned while the chat input was open.

## Highlights

- **Answers arrive in Markdown while they stream, and stay on their first page.** Bold, headings and lists show as the answer comes in (Markdown While Streaming, on by default), and Auto-scroll is off, so you read from the top at your own pace while the rest arrives.
- **The minimal popup shows its answer the way the chat window does** (bold, lists, the right fonts), as a floating box or a footnote panel; set to Always, it scrolls a long answer.
- **Proper fonts for Arabic, Persian, Urdu, Hebrew, Devanagari and emoji**, with nothing to install, and right-to-left lines and tables laid out in the right direction.
- **X-Ray names you control**: one Names and matching… screen, capitals only (decided automatically from how the book writes each name), and names with an apostrophe or a hyphen found in typeset books.
- **X-Ray**: a Conclusion once it reaches the end of the book, a Who's who preset, First appears and Last seen on an entry's page, and a creation form that says what each way to build gives.
- **AI merge between books is experimental for now**; what the earlier books know is still carried over on its own, for free.
- **Pictures**: one popup with your note, the X-Ray entries to draw from and every picture setting, and a picture remembers the entries it shows.
- **New models** (Claude Fable 5.2, GPT-6.2 Sol and Astra, Gemini 4 Carbon and Hydrogen, Qwen4-Max, Kimi K3, Mistral Large 4) **and Amazon Bedrock** as a provider.
- **Crashes and freezes fixed**: a rare crash a few seconds after background work, a freeze when the screen turned with the chat input open, waits that stopped on some Android e-readers until a touch, and a slow start.
- **Your own writing and your backups are safer**: a deleted book's notebook is kept, a backup that cannot be written whole says so, and a Merge restore keeps what you made since the backup.

## What Works Differently After the Update

- A streamed answer stays on its first page while the rest arrives (Auto-scroll Streaming is off by default now), so you read at your own pace and turn the pages yourself; the finished chat opens on the page you are on. The update turns the switch off once for everyone; turn it on again under Settings → Chat & Export Settings → Streaming, or tap the window's Autoscroll button to follow one answer. An X-Ray build is still followed.
- Answers are rendered while they stream (Markdown While Streaming, on by default; Settings → Chat & Export Settings → Streaming turns it off): bold, headings, lists and every script in its own face, instead of plain text swapped for the rendered view at the end. A phrase is bold from its first letter, a link shows its words while its address arrives and a table grows one whole row at a time; on a slow device, or as the answer grows, it is drawn less often. It applies to answers shown in Markdown, not to an X-Ray build, whose answer is data, and never to hidden streams.
- The newest reply opens its own page: your question, the usage line (reasoning, web search, book lookups) and the KOAssistant label stay on the page before, and the page you land on starts with the reply's first line, the first answer of a chat included. A chat that opens at the top instead (Open Chats at Latest Exchange off, the Chat button of a dictionary or translate window) keeps the label with its reply, as before.
- The three plain-text switches for right-to-left text are gone (Auto RTL mode for Chat, Text Mode for RTL Dictionary, Text Mode for RTL Translate): every window stays in your View Mode whatever the language, each paragraph laid out in its own direction and each script in its own face. A switch you had on is cleared, so the Markdown view shows, and a dictionary window of a right-to-left language, which opened in plain text by default, now opens in Markdown; Text Mode for Dictionary and the MD ON / TXT ON button remain your plain-text choices.
- **AI merge between books is experimental for now.** How well it links names that differ between two books has not been measured, and for most series the free carry already brings over what the earlier books know. It stays in an X-Ray's **Link and merge…** group. The app no longer offers it before a new X-Ray in a series, and the Group Hub has no row for it. It is being reworked for a later release.
- Quick Explain uses your domain and the book's Background note, as Explain does: the two differ in length and model, not in what they know. It left both out until now. To have that back, hold Quick Explain, tap Edit… and set its Domain to None.
- The X-Ray action's long-press menu no longer offers Without book info: an X-Ray is built by many requests, and the choice reached the first one at most (a build in checkpoints ignored it and named the book). To build an X-Ray that never names the book, set Book info to None for that book (Book Settings → Privacy & Data).
- A deleted book's notebook is kept. When you delete a book in KOReader, its KOAssistant notebook is moved to the KOAssistant notebooks folder under the book's name, a message says where it is, and Browse Notebooks lists it as a book that is not on this device (View, Delete Notebook). Until now it was deleted with the book's other KOAssistant files, though it is the one of them that can hold your own writing. The book's chats and saved results are still deleted with it, and a whole folder deleted in KOReader takes the notebooks inside it along.

## Crashes and Freezes Fixed

- Fixed a crash that could close KOReader a few seconds after work in the background finished: the name index's pass after an X-Ray is built or its book opened, Fetch models, Test provider, the update check, a search of the book's text, a picture request and the subscription sign-in read their result into memory that could already have been released. It was rare and looked random.
- KOReader no longer freezes when the screen turns (an Android device with rotation on) or its window is resized while KOAssistant's chat input is open; the box is laid out again for the new size with what you typed. The freeze was in v0.24.1 and earlier releases.
- On Android e-readers that sleep a few seconds after the last touch (a Boox, for one), a lookup, a download or a book search no longer stops until you touch the screen: every wait keeps something moving (the seconds and dots under a waiting message, dots after an answer that pauses), which keeps the device awake (ref #126).
- Fetch models from provider and Test provider no longer freeze the app while they run: each waits behind a message with the seconds and moving dots (Test provider's names its step), a tap on the message stops it, and on an e-reader that sleeps between screen updates they no longer pause until a touch (ref #126).
- KOReader no longer exits when a held word, a lookup or a PDF mention carries a damaged character, or when Generate Image is tapped on a highlight that crosses an indented paragraph: such text reached the case fold of the name matching, which KOReader's library cannot take.
- KOReader no longer starts slowly every time because one book's data could not be moved out of KOReader's metadata files (the one-time move of v0.22.0, for readers who used the plugin before it): the move went through every book in your history again at each start. It now runs once, and a book it could not move is moved the next time KOAssistant reads it (opening the book, its chats or its Book Hub).
- Building the underline index for a book with thousands of entities (a long series with carried entries) no longer freezes the reader for seconds: the pass that finds names inside longer names is hashed (about 40 times faster at two thousand entities).
- Book Settings → Privacy & Data: the Reading position, Library and Reading habits rows no longer crash on their "For this book" tab (those three kinds have no per-book value, so the tab is gone).
- A quiz question with an empty field from the model no longer crashes the quiz window on Show Answer or on export.

## Chat Windows and Streaming

### Streaming

- While an answer streams, dots move after the window's title from the first words to the end: with the page standing still, they show that the rest is still arriving.
- When a streamed answer finishes, the chat window takes the stream window's place without a shift: the two share one frame, one title bar and one place for the text, so an answer of one page does not move (its first line stood most of a line higher in the chat window, and a word could wrap onto another line). The stream window's title is in the regular face, as the chat window's.
- After pausing the follow in the streaming window, the chat lands on the copy of the phrase you were reading when that phrase repeats inside the reply, in Markdown and in plain text; it landed on the first copy.
- In the plain text stream view, a window that does not follow the text was redrawn with the screen's fast refresh, which is black and white only on e-ink: the text looked rough until the answer was complete. It is drawn like the Markdown view now.
- A streamed answer whose last chunk carries both text and the stop reason keeps that text; some hosts send the last words with the stop.
- Tapping Stop while a repaint of the streaming window is queued no longer paints the closed window once more.

### The minimal popup

- The minimal popup shows its answer the way the chat window would: bold, italics, lists, each script in its own face and each paragraph in its own direction (it was plain text, and an italic showed its asterisks). It is as wide as the chat window, and with Always a long answer scrolls inside it (a swipe, or the page-turn keys) instead of being cut off.
- New: Popup Style (Settings → Minimal Popup, and the tile's hold menu). The minimal popup can be a floating box next to the selection, as before, or a footnote panel at the bottom of the screen from edge to edge, like KOReader's footnote popups. The X-Ray card's Floating Popup is the same box, so it is wider too and scrolls a long entry.
- A word held in the minimal popup is looked up, and a longer selection or a long hold opens the selection popup (Copy, Dictionary, Translate and the rest), as in the chat window. The popup stays underneath.
- The Minimal Popup quick settings (a long-press on its Quick Settings tile) show a double line between their two settings rows and the list of actions.

### The Markdown and Plain Text views

- A numbered list keeps the numbers the answer wrote. Items with blank lines between them count 1, 2, 3 (they showed 1, 1, 1, since each became a list of its own); a list that goes on after a paragraph, a quote, a code block, a table or bullets, or that starts past 1, is shown with the answer's own numbers instead of starting again at 1.
- Task lists (`- [ ] to do`, `- [x] done`) are drawn as boxes, ☐ and ☑, in the Markdown and the Plain Text view; they showed their brackets.
- A message you typed with line breaks in it is shown with each line as a paragraph of its own in the Markdown view (it was joined into one block); a list or code you typed is shown as before.
- A highlight of several paragraphs is quoted at the top of a chat with its paragraphs apart (the Markdown view showed it as one block).
- A code block under a list item (a numbered step with its command) no longer turns the whole answer into raw text when the answer stops inside the block, or, with Markdown While Streaming, while the block is still arriving.
- In the Markdown view, two marked words side by side (bold then italic, two code spans, two links in a row) keep the space between them; since v0.24.0 they ran together.
- A word in a table's narrow column is no longer split over two lines (in a column of single words a word could be broken after a letter or two, or lose its full stop to the next line).
- In the Plain Text view the window opens on the newest reply's first line. In a chat of several exchanges it opened some lines above it, further off with every exchange, with a cursor mark in the text.
- Emoji and other characters outside the basic plane are shown whole when a provider sends them as escape pairs (many self-hosted servers do): they came out as six replacement characters and were saved broken in the chat.
- Changing the font size or the alignment, Reset to Defaults, and Hide/Show Original in a translate window keep the rendered math and the right-to-left alignment; they rebuilt the view without them until the chat was reopened.
- The chat window's reasoning line no longer appears for a request that sent no reasoning setting at all.

### Right-to-left text and other scripts

- The Markdown view draws each script in its own face. Arabic, Persian and Urdu letters come in Noto Naskh Arabic, the face KOReader gives Arabic books, with real bold, wherever they appear: a whole paragraph or a word quoted inside an English sentence (they had a plain serif fallback). Hebrew and Devanagari take the faces KOReader's own interface uses for them, and emoji are drawn with the plugin's bundled emoji font, no install needed (they showed as boxes).
- A new row, Settings → Display Settings → Rendering → Right-to-left text font, picks Noto Sans Arabic UI (the face of KOReader's own text windows), any font KOReader knows, or None. The plugin keeps a copy of each font it draws with in `koassistant_fonts/` under KOReader's data folder (safe to delete, refilled when needed): KOReader's builds from November 2026 on read a window's fonts only from a folder the window hands them.
- In the Markdown view, a line that begins in the answer's own language keeps that language's direction: in an English answer, a label such as "Synonyms:" followed by Arabic words stays on the left (it was laid out right-to-left, the label on the right with its colon before it), and each message of a chat is judged on its own.
- A dictionary window that shows the book's sentence above the answer judges the answer by its own words: an English definition under an Arabic sentence stays left-to-right even where it opens with the Arabic headword (the sentence's words outvoted it, and the definition was laid out right-to-left, its full stop on the left).
- In the Plain Text view and the minimal popup, a line that mixes right-to-left and Latin words takes the direction the Markdown view gives it: an Arabic sentence with an English name in it is laid out right-to-left (every mixed line was laid out left-to-right, so such a sentence came out in the wrong order), and an English definition that opens with an Arabic headword stays left-to-right.
- A table in a right-to-left answer is laid out right-to-left: its first column is on the right, each cell's text starts at the right of its cell, and an English cell keeps its full stop at its end (every cell's text sat on the far side of its cell, and English cells were laid out right-to-left). A table too wide for a grid, shown as lines, has its rule on the right. A table with an Arabic column in an English answer keeps its order.

### A turned screen or a resized window

- Rotating the device, resizing the screen, switching the window size or switching a chat between Markdown and Plain Text keeps your place: the window shows the text you were reading. A rebuilt window used to open at the top, and the view switch went back to the chat's start.
- After a turn, Save Chat, New Tag and the reply box stay on top of the chat window with what you typed (the rebuilt chat window covered them), and the chat window opens on the page that holds your place also when your top line began with a page's last word (it showed the page before).
- On a device whose own rotation sensor KOReader reads (some Kobo and Kindle models), turning it with a chat window open turns the screen and the chat window follows; the screen used to stay as it was.
- After a rotation, the Save Chat and New Tag dialogs' buttons act on the dialog on screen.

## X-Ray

### Building an X-Ray

- An X-Ray that reaches the end of the book ends with a **Conclusion**: the last checkpoint, an update to 100% and an X-Ray built with your position on the last page now ask for it in place of Current State (Current Position in nonfiction). Until now only a whole-book build in one request did, so a book finished in checkpoints still said what things were building toward. An X-Ray already at 100% keeps what it has until it is rebuilt.
- The X-Ray creation form says under the picked row what that way to build gives, in two or three sentences: one request is the cheapest and writes every entry with the whole book in view; checkpoints give a version for every stretch of the book and find more of the minor names and hard words, for more requests. A rebuild's form no longer opens with lines of text above its first row (its text ends with what happens to the X-Ray that is there), and the form no longer needs scrolling on an e-reader's screen. The wiki has the measured comparison.
- The X-Ray creation form says what you will be shown of an X-Ray built in checkpoints: under "In checkpoints, now" and "In checkpoints, as I read" a line of its own gives the book's own case (spoiler protection on: each checkpoint appears when you reach it; off: the newest checkpoint is shown as soon as it is built), and a tap on that line opens the book's Spoiler Protection setting. Both rows build the same versions either way.
- The creation form shows a gray **⚠ Fast model** line when the model in use is its provider's fast one and the pick is checkpoints or Deep depth; a tap on it says why: in our runs such a model mixed up people who share a name when it built in checkpoints, and kept them apart in one request.
- A new preset, **Who's who**: the cast alone, one line each, no Current State. The shortest and cheapest X-Ray; it is smaller, not more accurate.
- One name for the last section of an X-Ray wherever it is a setting: **Current State**, as the browser calls it (it was "status block" in the presets and Info, "Where things stand" in the picker). And the **Categories** button and rows list what is ticked ("People, Timeline", or "4 of 5" where room is short): they never show a preset's name, so "Preset: Reference" no longer stands above "Categories: Reference".
- The X-Ray's Info (the browser's ☰ menu) now says what it was built with: the preset, or Custom with its categories, depth and Current State. It reads the saved X-Ray's own record, so it is right for a version or a section X-Ray too.
- Reading along, a new person who only shares a name with someone already in the X-Ray no longer takes that person's entry over (a maid with her mistress's first name, a grandfather with the title and surname his grandson was first met under): they get an entry of their own, and the duplicate review can still merge two entries that are one. An update can no longer replace a description with an empty or a stub text.
- X-Rays are saved to their book again after a library dialog was open. Once a Library chat, a Series or Group chat or a multi-book compare had been opened, an X-Ray of the open book was shown in a chat window and not saved, and a checkpoint build stopped at its first step, until KOReader was restarted (ref #123).
- With spoiler protection on, a checkpoint build no longer installs a checkpoint ahead of where you are. Right after reading the book's text the plugin could read a wrong reading position (until the page was drawn again), and a checkpoint whose answer arrived in that moment was installed although it reached past your page.
- Large checkpoint chains pause at an oversized step for review again, and a one-step build offers its extra button; the safeguard read a flag the request had already cleared.
- The confirmation before an X-Ray is rebuilt in checkpoints no longer promises that the old version is archived when version archiving is off.
- Settings → Reading & Library → X-Ray: the Preset, Categories, Depth, Type and Carried Entries rows open their pickers again. They did nothing in v0.24.0 and v0.24.1 (the same defaults could be set from any book's Book Settings → X-Ray on the Global tab); reported with a tested patch in #123.
- "Delete All" artifacts (the artifact browser, the Book Hub) now pins the book's automatic X-Ray off as every other delete of a live X-Ray does, and the underlines of the open book go at once.

### Names, matching and underlines

- An entry's names have one screen, Names and matching…: every name, the main one included, says whether it is matched in the text, so a name that is also an everyday phrase can stop marking ordinary sentences. Renaming no longer asks about matching, your own names can be deleted, and Reset to the AI's names undoes it all.
- A name can be set to capitals only in Names and matching…: a faction named "The Drowned" then marks "the Drowned" but no longer "the drowned trees", in the underlines, the counts and KOReader's search after a mention.
- Capitals are decided automatically from how the book writes each name: once the book's names are indexed, a name written both ways, with its capitals at least three times mid-sentence and a quarter of the time, matches with capitals only. Names and matching… says "capitals only (automatic)" or "any case (automatic)", and a name's choices (Automatic, Capitals only, Any case, Not matched) mark the one in force and stay open when you pick another.
- A name's choices in Names and matching… say what the automatic rule saw: how many of its counted uses have its capitals, or that the book's names are not indexed yet.
- Capitals are decided automatically for upcoming entities too, the entries known only from the next checkpoint: a title the book also writes as a name ("my lady" against an entry named Lady) no longer underlines the lowercase word once the book's names are indexed.
- The automatic capitals and a name's counts are read from the stored layout that has the name, so a name first indexed after a font or orientation change is judged too; a page with a ligature, a superscript or a full-width mark no longer passes every later name's capitals unread; and a capital after an abbreviation's period ("No. 5. Summer") is no longer counted as a capital mid-sentence, with quotes of every tradition opening a sentence.
- Look up in X-Ray on a book with one X-Ray honours Not matched and Capitals only: a name set to not matched no longer opens its entry, and a capitals-only name opens it only when selected with its capitals. In PDFs, Mentions and Chapter Appearances no longer count a name inside a longer word ("Ann" in "Hannah").
- Names with an apostrophe or a hyphen now match a typeset book: the AI writes King's Landing or Mary-Jane with the plain characters, the book prints curly apostrophes and typographic hyphens, and no underline, count, card, lookup or chapter count found them. The book's name index is rebuilt once in the background.
- X-Ray names in Vietnamese, Hindi and the other Indic scripts, Hebrew, polytonic Greek and Georgian are matched as whole words: a short name counted inside longer words (underlines, Mentions, Chapter Appearances, the automatic capitals), as if those scripts had no word boundaries. The name index is rebuilt once per book for this.
- Looking up or searching an X-Ray name typed in capitals, or a lowercase one, finds it in every script (Cyrillic, Greek, accented Latin), not only in ASCII.
- Names in a Chinese or Japanese PDF keep their mentions, a name set to capitals only that starts with the Turkish dotted capital I or a full-width capital matches again, Armenian and Ethiopic names match before their script's own comma and full stop, and Look up in X-Ray finds a name with a typeset apostrophe or hyphen.
- Look up in X-Ray on a book with section X-Rays also starts its results with Add "…" as an alias…, so a first name that only partly matches an entry can be added to it there too.
- A change to an X-Ray shows in the page's underlines at once, with no page turn: a name added, renamed or set to capitals only, an entry merged or deleted.
- The Marking Density and Mark rows under Settings → Reading & Library → X-Ray redraw the underlines at once; a pick there used to show at the next book open.
- Turning the X-Ray underlines off (or a search closing) no longer cancels the background pass that builds the name index; Mentions and Chapter Appearances kept waiting for a pass that had been dropped.
- The Mentions view and Chapter Appearances skip the costly containment pass for names the text does not hold at all.
- Your X-Ray name edits (names, matching choices, never-merge pairs) are written through a temp file: a write cut short by a full card keeps the old file instead of leaving a torn one.

### Entries, cards and the browser

- An entry's page says where the book first writes its name and where you last saw it, chapter and page (**First appears**, **Last seen**). It is read from the book's own name index, so it costs no request; with spoiler protection on, the last place is the last one up to where you have read. In EPUBs, once the index holds the entry's names.
- The X-Ray card set to **Card Shows: Full entry** shows the entry's own text: its description and what its page has under it (other names, Details, Evidence, Significance, what other books add). It showed the description alone, so an entry's Significance never reached the card. Its connections stay on the entry's page.
- The X-Ray card's footnote panel shows Arabic, Persian, Urdu, Hebrew and Devanagari names and text in the same faces as the chat windows (your Right-to-left text font for Arabic script); it used a fallback face whatever was set.
- An upcoming entity's card offers its one-line description on a tap for every name, a first name or a nickname included; before, only a tap on the entry's exact name got it.
- An upcoming entity's full entry opens behind its confirmation whatever the spoiler setting, and the confirmation box and its page both offer Matching…, the names' choices for an entry the X-Ray browser cannot hold yet, so a wrong underline is switched off without reading the entry.
- An upcoming entity's confirmation box lists, under Matching…, the name you tapped alone: it used to be titled with the entry's name and to list every alias, which gave away whose nickname you had tapped before you chose to reveal it. The full entry's Matching… still lists every name.
- The help texts of Entity Card First, Upcoming Entity Cards, Card Style and Spoiler Protection describe the card as it is: the next checkpoint past your position, the stages, the confirmation whatever the spoiler setting, a Finished book unprotected.
- A chat started from an X-Ray entry by tapping one of the dialog's actions (Explain, ELI5 and the others) is listed on the X-Ray browser's X-Ray chats row; only a chat started with a typed question was. Chats saved before this stay in the book's Chat History.
- A Story Arc entry, or an Argument Development entry of a nonfiction X-Ray, no longer repeats the names it links to under its text (they are its buttons), and a chat about an Argument Development entry no longer calls its concepts and key figures "Characters".
- Merge with another entry… keeps the entry page open while you pick: Cancel or Back returns to it, and a merge opens the entry you kept instead of the X-Ray's first page.
- After you tap a mention, the magnifier in KOReader's search window opens the search box on the entry's name instead of your own last search.
- An X-Ray lookup from an entity card or the dictionary bypass is about the open book, even after a chat about another book from the file browser.
- A chat or an AI Wiki article about an X-Ray entry of another book than the open one uses that book's own domain, languages, research mode and spoiler setting, not the open book's.
- The duplicate-entities offer after an X-Ray install no longer appears over the file browser when the book was closed in the meantime, and no longer spends the pair's one offer there.

## Book Groups and Series

- Carried entries follow the group: when a book leaves a group, a group is deleted, a series is put in another order or a group changes kind, each X-Ray drops the carried entries and "From" lines of the books it no longer takes from (in a series, never a later book). What an AI merge added stays, and so do the entries you carried or added by hand.
- An earlier book's entry is carried even when this book has an entry of another kind by a similar name (the character "the Warden" beside the term "Warden"), and its read-only view no longer says it is already in this book's X-Ray.
- In a series, the Group Hub's book rows hold a later volume back as the → Group list does: the row says (later in the series) and asks before that volume's Book Hub opens, when the hub was reached from an earlier book.
- Move back to carried list is offered only on entries you added from the carried list, no longer on every entry that has history from another book.
- An X-Ray update or rebuild, and a checkpoint install, no longer forget the AI merges the X-Ray holds, so AI merging a series no longer runs merges again that were already done.
- A carried entry seeded from an earlier book before that book's entry had aliases now receives the aliases a later re-seed brings.
- "Add to <group>" in a book's Groups popup no longer leaves two copies of the popup.
- Adding a folder, a collection or a series' books to a group writes the groups file once, not once per book; so does ordering a series by its index.
- With thirteen or more X-Rayed books in a group, every page turn re-parsed every one of them (the memo was wiped at twelve); the memo now keeps the books of the walk in progress.

## Dictionary, Translation and Selections

- KOReader's own dictionary is reachable while the dictionary bypass is on: KOReader's Dictionary row in the highlight menu (a very long press on a word opens that menu) opens KOReader's dictionary, also for a word that is an X-Ray name; it ran the bypass action or opened the X-Ray entry. Dictionary (KOA) stays KOAssistant's action.
- Dictionary in the selection popup of a chat window, an X-Ray page or any other KOAssistant window opens the dictionary also for a word that is an X-Ray name; it opened the entry, which Look up in X-Ray beside it already does.
- A word tapped in the Vocabulary builder's review list opens in KOReader's dictionary again, with the builder's Forgot and Got it buttons, when the dictionary bypass is on or the word is an X-Ray name (it went to the bypass action or the X-Ray entry, and the two buttons never showed).
- The two Bypass Action rows name your own actions; a bypass whose action was deleted says so once and opens KOReader's dictionary or the highlight menu, and deleting an action clears a bypass that pointed at it.
- The dictionary popup's "Look up in X-Ray" and "Generate Image" buttons, and the dictionary bypass, no longer act on a book you chatted about earlier from the file browser or a Book Hub: they take the open book (or the chat's own book).
- The Deep Analysis dictionary action is found by its id again (a custom action override, a bypass or a gesture pointing at it works).
- After a word lookup inside one of KOReader's HTML text windows the word's highlight is cleared, as in the plain-text ones.
- In a translate window every line is its own paragraph, the original's and the translation's alike: Translate Page showed a page's paragraphs as one block in the Markdown view whenever the model answered with single line breaks, which is how KOReader hands the page over. A PDF or DjVu page, whose text comes as printed lines, keeps its lines joined as before.
- In a translate window in the Plain Text view, Show Original no longer changes the line spacing.
- The sentence around a selection ends at 。！？ (Chinese and Japanese), । (Hindi) and ؟ (Arabic) too; those scripts write no space after the mark, so a sentence-sized context kept the whole paragraph.
- A prompt line or typed text that happens to say "In context" is no longer dropped when the dictionary context is off; only the line holding the context placeholder goes.

## Image Generation

- Generate Image opens a popup on a tap: a note and the X-Ray entries the prompt writer will read (at first the ones the passage names, carried entries included, up to five, to change by hand), then Prompt, Style, Shape, Detail, Provider and Model, two to a row, each a button showing its value, where a change is the setting itself.
- Illustrate… and a gallery picture's Image settings… open the same popup: Illustrate with a note for this picture, the gallery's with Regenerate and Regenerate and replace.
- A picture remembers the X-Ray entries it shows, and an entry's More… has Pictures (N)… beside Illustrate…, opening the gallery on its pictures.
- A note that names a character or place brings that X-Ray entry to the prompt writer, so a passage that only says "she" can still be drawn right.
- The prompt writer reads more of the text around the passage (up to 1,000 characters on each side, up from 400) and takes the setting from the passage's own moment: where nothing says where the moment happens, it keeps the background simple instead of inventing a room and its furniture, and it keeps characters' names out of the prompt while saying who they are (their people, age and role) when the book does. The note box's hint now starts with the setting or context, the place to say it.
- Illustrate draws a person or a thing on a simple background unless its X-Ray description says where it is, instead of inventing a room around them; a place named in the note still gives it one.
- The prompt writer now uses your chat model instead of its provider's fast model, which followed the writer's rules less closely; the new Settings → Advanced → Image Generation → Prompt writer switches back to the fast model, quicker and cheaper.
- A picture arrives sooner on a slow reader once the provider has answered: a large answer (one model sends 10 MB for a picture) is read in quickly instead of a little at a time, which could add half a minute, and the window says "Saving the picture…" while the picture is saved and opened.
- The picture window's dots move while it waits, as chat's do: on an Onyx Boox the window had frozen about ten seconds in, until the screen was tapped.
- The image prompt writer and the picture popup's entry list honour a name set to "Match capitals only": a passage saying "will" no longer names an entry called Will.

## Providers and Models

### New models and providers

- More new models, each probed on 2026-11-18: Claude Fable 5.2 is Anthropic's most capable pick (it always thinks; Fable 5.1 stays listed), GPT-6.2 Sol and Astra are OpenAI's flagship and most capable picks (neither can turn reasoning off; GPT-6.1 Sol and GPT-6 Astra stay listed), Gemini 4 Carbon (Google's strongest, paid only) and Gemini 4 Hydrogen (its general-purpose model) join the Gemini list, and Qwen4-Max is Qwen's default. The same models appear where OpenRouter, Perplexity, A2Agent and Requesty serve them.
- New models, each probed: GPT-6.1 Terra is OpenAI's default (it reasons by default and can be turned off; gpt-5.6-terra stays listed), Mistral Large 4 is Mistral's default (the Large alias is refused on the free plan, which also allows no requests on Medium, Small or Magistral), Kimi K3 is Kimi's default with K3.1 Pro as the flagship (Moonshot closed K2.6 to new accounts and retires it in late December; the two older Kimi ids move to K3), Fireworks' default is DeepSeek V4.1 Flash (gpt-oss-120b leaves its serverless endpoints on 2026-11-07; a saved pick of either gpt-oss id moves), A2Agent's default is DeepSeek V4.1 Flash 1017 with MiniMax M3.1 Flash beside it, and the same new models appear where Model Studio, Fireworks, Perplexity, OpenCode Zen, NVIDIA (Step 5 preview, Nemotron 3.5 Bolt) and OpenRouter serve them. GPT-5.6 now counts as reasoning by default, so its Off setting is sent as "none".
- Amazon Bedrock is a built-in provider (community, docs-based; contributed in #113): a Bedrock API key and a region picked under Settings → Advanced → Provider Settings, every model the account enables in that region (Fetch models lists them), book tools on the models the contributor probed. Answers arrive whole for now (no streaming), and reasoning settings do not reach it yet.
- Image generation: gpt-image-2.6-flare is OpenAI's default picture model with gpt-image-2.6-sunburst beside it; a saved pick of gpt-image-1, which OpenAI shut down, moves to gpt-image-2.5-flare.
- The dated retirements are taken ahead of their dates: a saved pick of claude-sonnet-4-5-20250929 is sent as Claude Sonnet 5.5, gemini-2.5-pro as Gemini 3.8 Flash, gemini-2.5-flash as Gemini 3.5 Flash Lite and kimi-k2.6 as Kimi K3, which leaves the Kimi list; gpt-image-1-mini leaves the OpenAI image list and a saved pick draws with gpt-image-2.5-flare. The startup notice for a moved pick says the provider retired the model or is about to.
- NVIDIA ended openai/gpt-oss-20b on November 18: its fast speed tier uses Nemotron 3.5 Bolt now, a saved pick of the ended model moves there, and Mistral Large 4 joins NVIDIA's list. SambaNova no longer serves Llama 3.3 70B (a saved pick moves to gpt-oss-120b), and Qwen's Standard speed tier moved from qwen3.5-plus, which Qwen retires on January 19, 2027, to qwen3.8-flash.
- SambaNova, Together and OpenCode Go: models their catalogs no longer serve (SambaNova's DeepSeek V3.1 and V3.2 and MiniMax M3, Together's DeepSeek V4 Flash 0731, OpenCode Go's MiMo v2.5 pair) are replaced by the ids they serve now, and a saved pick of a gone model moves to its replacement.

### API keys, provider tools and cost

- The API key window's gray note says to check the start of a key copied in KOReader: a selection that does not begin on the key's first character leaves out its first few characters (the "AQ." of a new Gemini key, the "sk-" of an OpenAI key), and the provider then answers "API key not valid" (#125).
- A key you save in the API key window is the one in use from then on: a key added with Add API key... used to wait behind the first one until tapped in the key list, so a reader replacing a dead key kept sending it (#125).
- When a provider refuses a request for its key ("API key not valid", an authentication error), the error names the key that was sent: its name, where it came from (the app or apikeys.lua), its first 3 characters and its length, so a key that lost its start or is not the one you meant shows right there (#125).
- Test provider no longer calls a correct OpenAI or DeepSeek answer unreadable.
- Test provider: a model that refuses a forced tool call is no longer recorded as taking tools (the book tools' gather round could not use it).
- An X-Ray, a summary or any other saved result built with Claude (Anthropic directly, or through OpenRouter) no longer pays the prompt cache's write surcharge for the book's text, since no later request reads that cache: an X-Ray of a whole book costs about 18% less (measured on Claude Sonnet 5.5). Chats keep their cache as before.
- A result saved for one section (a section X-Ray, a section summary, a chapter quiz) built with Claude no longer pays that surcharge either.
- Saving a first API key no longer switches the provider of a reader using the OpenAI Subscription, Ollama or a configuration.lua key; a switch picks the new provider's default model.
- Settings → Model: "Add custom model…" in another provider's panel now selects that provider with the model; removing or clearing custom models only resets the selection when it belonged to the active provider.
- Quick Settings, the reasoning popup, the Model row's label and the temperature note name the provider in use for a reader whose provider is set in configuration.lua; they said Anthropic.

### Answers, limits and reasoning

- An answer the provider cut at its output limit is now marked as cut on every provider, not only Anthropic, OpenAI, Gemini, DeepSeek, NVIDIA and Z.AI, so a cut X-Ray step or summary is no longer saved as if it were whole.
- On e-readers and Android, a provider's error shown while an answer streams keeps its HTTP status and the provider's own reason (it showed the bare message), so the tip under it fits: an account out of credit is no longer told it hit a rate limit and offered Try again.
- Answers from servers that end a normal answer with `eos` or `eos_token` (text-generation-inference and the hosts built on it, reached as a custom provider) are no longer marked as stopped early, so X-Rays and other saved results are kept there.
- A model the provider retired (sent as its replacement) takes the replacement's reasoning settings, so an "off" that the old model understood no longer sends a value the new one refuses.
- A reasoning level the model does not offer (a setting kept from another model, an action's level from another provider) falls back to the model's default level instead of being sent as is and refused.
- OpenRouter: a model whose output limit was learned from a rejection before its capabilities were fetched keeps its reasoning and tools; the learned entry read as "supports nothing".

## Privacy and Data

- With Book info on None, a request that carries your notebook no longer names the book: the title line KOAssistant writes at the top of a notebook file went along with the notebook. Requests now carry the notebook's entries without that line, at every Book info level.
- Book info set to Title only leaves the author out of the prompt's own words too ({author} and {author_clause} resolve to nothing), as it already left the author out of the context line.
- Page bookmarks are no longer sent or counted as highlights: KOReader keeps them in the same list, so a bookmarked page's first words rode along with your highlights, and the data question counted them.
- An X-Ray that was built when X-Rays also read your highlights can be continued again with Highlights on Ask: the data question names the saved X-Ray and what it was built with, and Allow once covers it. Before, an update was sent as a full rebuild and a background or checkpoint update did nothing.
- A result built with your notes (Analyze Notes, for one) is saved as built with notes, so a chat about it, attaching it or updating it asks for notes; it was saved as built with highlights alone. Results saved earlier keep their old label until they are updated or redone.
- A chat that was given your highlights without your notes (notes refused) is recorded that way: continuing it with another provider was asked about, or refused over, notes it never held.
- Pinned answers keep the record of what they were built from (the book's text, highlights, notes, the notebook) and which provider answered, so a chat about a pin, or attaching it, asks the data question the same way as any stored result.
- Settings → Privacy & Data → Reading position says when the position is sent: only where something uses it (an action that asks for it, the spoiler reminder while protection is on, and every request only when Book info is set to Title, author & position). The setting did not change; its text read as "always sent".
- AI Wiki from a highlight or the dictionary popup asks for the text around the selection when that kind is on Ask, as the X-Ray browser's AI Wiki does; before, the text was dropped silently.
- The reading position line of a Send follows the provider a long-press pick sends it to.
- Cancelling the data question leaves nothing behind: a run option, the chips' state or a scope pick set for the cancelled run no longer rides the next request.
- Reading habits count a book opened under two ids (a move, a re-import) once, with its reading time summed; the last row read used to win.

## Actions, Menus and Settings

- An action run on one section of a book (Document Summary, Key Arguments, a quiz, the Reading Guide and the others) asks about that section alone: the request no longer also says "summarize the book" and "cover the entire work", which made a small model reply that it could not summarize a whole book from one chapter. A run up to your position gives the model your real position where it said 100%.
- Saving one of your own actions keeps what you did not change: Quick Edit and the full editor dropped the action's domain, its Quick switch, its temperature and maximum length, its spoiler and surrounding-text settings and its description at a Save, changed or not, and the full editor turned Web "Never" into "Follow global". Duplicate keeps the action's domain, and from Manage Actions its spoiler and surrounding-text settings and requirements too.
- A built-in action saved with nothing changed stores nothing (it stored the shipped temperature, reasoning and behavior, showed the changed mark and stopped following releases), and a Save from Manage Actions no longer erases a built-in's own domain. A stored change that only repeats the shipped values is dropped at the next Save.
- A built-in action that leaves your domain out by default (Translate, Fact Check, the library actions and the others, now listed in the wiki) can be given it: Domain: Global in its settings is saved. The pick was dropped at Save, so the action went on leaving the domain out.
- A custom_actions.lua that fails to load no longer strips its actions from every menu for good: their places are kept until the file loads again, and the first time you use KOAssistant after a start a notice names the error and its line.
- Deleting one of your own actions removes its gestures with it, and Settings → Gestures lists a gesture whose action no longer exists, with Remove, instead of leaving it out (KOReader's gesture manager showed it as Unknown item).
- Removing a default such as News Update from the gesture menu now sticks; it came back whenever the gesture list was read.
- The highlight menu shows up to 30 KOAssistant actions (15 before); members past the cap were silently left out while the ordering manager listed them as shown.
- The X-Ray popup and the other result popups (View, Update, Regenerate) end with **Close**, not Cancel: closing the popup cancels nothing, and a build that is running goes on.
- On a device with keys, Back closes the scope and source popup and the X-Ray creation form, as it closes other dialogs.
- Cancelling a section picker (Focus on a section, Start from a section, a range, Generate Section X-Ray) or its name input returns to the popup that opened it instead of leaving you on the page.
- Closing the reasoning model list, or cancelling the Quick Answer preset's model pickers (a tier, a provider, a model), returns to the screen that opened them instead of leaving you on the page.
- The chat input's Domain chip opens the same Domain & Research screen as Book Settings, with its Follow group row: a book that followed its group's domain stopped following as soon as the chip's own list was tapped.
- Domain & Research: a book whose Research mode is set to Off shows Off, not "Not set", when the global setting is on.
- Editing a custom domain or behavior and picking "Use as Template" fills the editor with the template; it kept the entry's own text.
- A deleted custom domain or behavior's id is never given to a new one: a book or action set to the deleted entry used to follow the new one silently.
- Restore defaults on custom behaviors and Fresh Start no longer let a new behavior or domain take the id of a deleted one.
- A custom action's hallucination reminder no longer tells the model to search the web when a run option or the Quick preset turned web search off for that request.
- The reminder against made-up facts now follows a run option's web pick and the Quick preset; the earlier fix read those values after the request had used them up.
- Show Debug names the behavior and the domain the request carried: it named your settings, so an action that leaves the domain out (Translate, Grammar) or a book with its own domain still read as your global domain. It also says when the book's Background note went along.
- The Setup Wizard's icons step says what the emoji font is for when the icons are off, which is how they start; it told a new reader that the icons "show as empty boxes".
- Setup Wizard, Connection: cancelling the key entry (Cancel, an empty Save, the Back key) returns to the provider list instead of leaving the wizard.
- Settings → Setup Wizard → Icons: after "Install" and "Restart now", the next start shows the glyph test alone instead of running the whole wizard chain.
- KOReader's Irish, Indonesian and Slovenian UI languages are detected as the response language at first start; they fell back to English.
- The notice about a configuration.lua that failed to load is shown once per session, not at every switch between the file browser and a book.
- The Translate button on the release notes popup uses your current provider instead of the one seeded at first start.

## Chats, Attachments and Book Tools

- A reply no longer sends the chat's first question twice: every reply carried it inside the chat's opening message and once more as a message of its own, which cost its length again each time and which a model could remark on.
- A provider's empty "reasoning" or "content" field (a JSON null) no longer corrupts the saved chats file; chats saved after such an answer load again.
- Asking for an answer in another language works ("answer in Arabic", written in your own language): the language instruction allowed a switch only when your message itself was written in another of your languages, so a model that followed it stayed in your primary language.
- After continuing a chat from Chat History, a saved result's window (a Summary, a Recap, an X-Ray's Full View) no longer acts on the continued chat's book: Add to Notebook wrote into that book's notebook and a held word was looked up in that book's X-Ray. Such a window always uses its own book, so Add to Notebook is offered there for it.
- Analyze Notes opened for another book (a Book Hub beside the open book): View, Delete, Regenerate and "Redo complete" act on that book, not on the open one.
- "Generate Analyze Notes (complete)" from a closed book's dialog (the file browser, a hub beside an open book) analyzes to 100%; it ran to the position with the spoiler framing.
- X-Ray, Recap and the other book-level runs started from Quick Actions right after a library chat no longer run as a library request (their answer was not saved) and no longer inherit that chat's Spoiler chip.
- A part of the book past your position that you confirmed for one message (the Scope chip) no longer switches the spoiler reminder off for the first message of the next chat.
- An action run from the file browser's long-press menu (Book info and the others), and Regenerate on a closed book's result, no longer take the last chat's Spoiler chip: a protected book could run unprotected.
- A chat about an artifact started with a run option (another model, No reasoning) keeps it past the data question; the request after the question ran on the main model.
- Library chats can be tagged; they answered "Cannot tag: no document context".
- Compare with KOAssistant on several selected books runs on the file browser in front of you; it was bound to the first plugin instance of the session.
- Attachments staged in a chat's input dialog are dropped, with a notice, when you run an action that takes none (one that saves a result, or a dictionary or translate action), instead of riding the first reply of its result's chat.
- Attaching a file that is not UTF-8 text (Latin-1, UTF-16) is refused with a notice instead of reaching the model as mojibake; a UTF-8 byte order mark is dropped.
- Braces inside a selection, typed text or the book's text stay as written: a "{title}" or "{highlights}" inside the text was treated as a placeholder and replaced.
- A scanned PDF (page images without a text layer) counts as having no text: an action asks "No text could be extracted" before it sends, instead of sending empty pages that passed for the book's text.
- Deleting a chat of a book that was moved or renamed updates the chat index under the book's current path; it wrote a stale entry under the old path and left the count wrong.
- Book tools: the note after a lookup that found nothing says "search the web" for the model the request goes to, the provider's default included; it read the model as unset.
- Book tools and the X-Ray's table of contents outline see a book's chapters even when KOReader has not built the table of contents yet (it builds it on first use); such a book read as having none.

## Notebooks, Backups and Updates

- Changing the notebook save location no longer removes the old notebook before the new copy is proven written; a failed copy (a full card) keeps the old file and counts as failed, and any notebook write that fails now says so.
- A backup fails with its reason when a file cannot be copied or written whole (a nearly full card) instead of reporting success with a file missing, and a restore that cannot make a complete restore point stops before it changes anything: a failed restore could say "rolled back" while chats or groups made since the backup were gone.
- A restore in Merge mode keeps what you made after the backup: book groups, general and library pinned answers and the custom domains, behaviors and providers created in the app are joined with the backup's (they were replaced by the backup's lists, so newer ones were gone), and no restore, in either mode, makes a new domain, behavior or group take the id of one it removed.
- A restore whose file copy fails (a full card) now fails as a whole, with the reason, and rolls back to the restore point; it reported success with files missing.
- After a restore, book groups and the menu placements of custom actions are no longer overwritten by what was in memory before it (they were, at the next change before a restart).
- A restored backup takes effect in this session: the next setting change no longer writes the pre-restore settings back over it.
- The warnings at the end of a restore (the keys you had are kept, a backup made by another plugin version, a skipped action) are translated like the rest of the screen.
- A failed automatic update check (Wi-Fi on, but GitHub unreachable) is no longer tried again each time you open or close a book: automatic attempts are at least 30 minutes apart, and a check that succeeded still holds for 24 hours.

## How You Can Help

- **Device reports.**
- **Translations**: review passes on [Weblate](https://hosted.weblate.org/engage/koassistant/).
- **Bug reports and feature requests.**

# v0.24.1 · 2026-10-20

# KOAssistant v0.24.1 Release Notes

This is a maintenance release for v0.24.0. Its notes follow below.

- Library actions let you pick their scan folders for each run: your default folders start ticked, recent ones are one tap away, and no folder has to be set beforehand.
- Book list is called Library Scan again, Permanent Scan Folders are Default Scan Folders, and the action editor's Library Scan box is on every custom action.
- The data question can skip the optional part: Continue without, or Allow once without your reading habits.
- Always allow sticks when started from Quick Actions, a gesture or the file browser, and More… opens Privacy & Data and asks again.
- No questions about data that isn't there, and Suggest Next Read on Finish works on Ask.
- In the library dialog the question names the ticked folders, and a chat with no books picked needs your library scan.
- Fixes: unticking every library folder no longer sends all of them; continued chats are checked for what they carried, against the provider they use; an X-Ray update's Allow once stays with it; the unread warning survives More…; saving a custom action keeps its Library Scan box.

---

## v0.24.0 Release Notes

KOAssistant now asks before it sends your data, a Setup Wizard checks what each update changed, pictures are written from the book and kept in a gallery, X-Rays get presets and carried entries in their categories, and the documentation moved to the wiki. The plugin's code moved into one folder, so restart KOReader right after the update.

### Highlights

- **KOAssistant asks before it sends your data.** Highlights, notes, notebook, book text, book list and reading habits are each Ask, Allow or Never, for all books, for trusted providers and per book. After the update every kind is on Ask.
- **A Setup Wizard for new installs and for updates**, and any KOReader gesture for the quick panels.
- **Pictures that match the book.** A prompt writer turns the passage, the X-Ray entries it names and your note into a picture in the style you pick, fitted to your screen; OpenRouter joins as an image provider, and a gallery keeps your pictures by book.
- **The documentation moved to the [wiki](https://github.com/zeeyado/koassistant.koplugin/wiki)**, and the README is the front door.
- **X-Ray presets, carried entries in their categories, and Possible matches** for names that changed between books.
- **Updates find their place after a font change, a turned device or a synced sidecar**, and moved books and folders keep their links.
- **New models and defaults** on Anthropic, Gemini, the OpenAI Subscription, Qwen, OpenCode Zen and NVIDIA, and new image models.
- **The plugin's code moved into one folder: restart KOReader right after the update** (on Android, close and reopen the app).

### Privacy

- **The question names the action, the provider and the amount**, and offers Allow once, Allow for this book, Not for this book and More…; your book list and reading habits offer Always allow instead. A kind set to Never is refused with a button to its setting. After the update every switch reads Ask; per-book settings and trusted providers are kept.
- **It is asked once per book, at the moment of need**: when an action starts, on the source popup's Run button, at Send with a Scope range or the Tools chip on, and when you attach or chat about your notebook. Viewing and browsing never ask.
- **One preset row: Default (Ask), Allow everything and Block everything**, in Settings → Privacy & Data → Preset. A note lists what a pick changed.
- **Book info moved to Settings → Privacy & Data, and None now means none**: nothing names the book, and actions that need the title say so instead of running.
- **Book Settings → Privacy & Data shows the book's values and the global ones on two tabs**, and the Quick Settings tile of the same name opens it.
- **Groups can hold privacy values** for every member, in Group Settings → Privacy & Data. A group's Never works like a book's.
- **Trusted providers have their own column of values**, Allow by default, under Settings → Privacy & Data → What trusted providers may use.
- **The text around what you tap is its own kind of data**, allowed by default: the context of a highlight or a lookup, the current page, the text around an image's passage. Set to Never, it is now kept out everywhere.
- **Automatic X-Ray asks once per book** before it builds, and a build you start by hand asks once for all its checkpoints.
- **Saved results follow what they were built from.** Chatting about an artifact, attaching one, or the AI Wiki asks for those kinds, and is refused when one is Never for the book.
- **AI merges ask once before their requests, and the free carry between a group's books works on Ask**; only a book set to Never stays out.
- **A chat remembers what it was given** and checks it again when you continue it, or continue it with another provider.
- **Delete Book Artifacts left the privacy screen.** A book's artifacts are deleted from its Book Hub or the artifact browser.
- **An X-Ray entry page lists your matching highlights whatever the highlights value**, since they stay on the device until you chat about the entry.
- **Rows and chips that need a kind on Ask are offered**, not grayed out; only Never grays them.
- **The note above an answer made without some data says why**, in your language.
- **Every privacy check judges the provider the request really goes to**, a model picked by holding Send or by the Quick preset included, and an action on a closed book checks that book's own settings.
- **Updating an artifact whose action does not use book text sends no new text.**
- **Attachments ride chats and plain actions only**, never an action that saves a result, nor the dictionary and translate actions.

### Actions and Menus

- **The Setup Wizard has two faces.** A fresh install gets the welcome chain: provider, privacy, language, icons and font, the (KOA) mark, gestures. After an update it checks only what the version changed, and Settings → Setup Wizard re-runs any step.
- **Any KOReader gesture for the quick panels and gesture actions**, from Settings → Gestures or the wizard. A gesture in use can be replaced.
- **The emoji font installs from Settings** (Display Settings → Emoji → Emoji Font), with a display test that turns the icons on.
- **Run an action once without the book info, or with it**, from its long-press menu. In a book chat, the gear menu's Send book info switches it for that chat.
- **Quick is clearer.** Each action's editor has a Takes the Quick preset box that decides whether Quick reaches it, the buttons that take Quick carry a ⚡ mark, and Quick's Book tools off reaches Explain in Context.
- **The scope popup follows the chat's Spoiler chip** for that run.
- **The (🔍) mark shows whenever an action could search the book**, not only with the book's text on Allow and the Tools chip on.
- **+Vocab stores the word as KOReader does**, and no longer says Added while the Vocabulary builder is off.
- **"Compare with KOAssistant" shows in the file browser's selection menu in every language.**
- **The sample custom actions file loads again**, and an action with an unknown context is skipped with a log line.
- **The long-press menu no longer offers Duplicate for X-Ray.**
- **Placeholders**: the surrounding-context placeholder in your own actions always brings the context, a placeholder with nothing behind it is dropped instead of sent as written, and a book action from the file browser can read your library list again.

### Image Generation

- **The image prompt writer.** Your chat provider's fast model writes the prompt from the passage, the text around it, the X-Ray entries it names and your note. The privacy question names both providers, and Write the prompt with AI turns it off.
- **A style for every picture**: Book illustration, Watercolor, Ink drawing, Pencil sketch, Woodcut, Photographic, Comic, Map or diagram, or your own words.
- **A note for one picture**: long-press Generate Image for Generate with a note…, or type it in the highlight input dialog.
- **One Shape and one Detail setting for every image provider.** Shape fits your screen by default, and Detail starts at Draft, the fastest and cheapest.
- **New image models**: GPT Image 2.5 flare as OpenAI's default, Nano Banana 2.1 on Gemini, Grok Imagine Image 2.0 on xAI.
- **OpenRouter makes images too**: GPT Image 2.5 Flare, Nano Banana 2.1, FLUX 3, Seedream and Recraft, and its whole image catalog under More models….
- **Generate Image shows whenever you have a key for an image provider**, and the first tap asks which one draws when your chat provider cannot.
- **A thumbnail gallery, by book.** Long-press a picture to draw it again, edit its prompt or delete it.
- **Image settings on the spot**: long-press Generate Image, or a picture in the gallery. Regenerate draws in the style now in effect, and Regenerate and replace swaps the old picture.
- **Gemini's Draft pictures come faster**: about 9 seconds instead of 13 to 23.
- **Image prompts follow chat's rules** for Book info, Context Direction and spoiler protection.
- **Clearer refusals and real file types**: a refusal names the provider's reason, Gemini image requests follow Gemini Content Filter, and Gemini's and xAI's pictures are saved as .jpg.
- **The image settings follow the provider that makes the images**, and a slow picture gets three minutes.

### X-Ray

- **Presets for new X-Rays**, from Characters only to Deep study, in the creation form, Book Settings, Group Settings and Settings.
- **"Where things stand" can be turned off** in the categories picker, which makes updates shorter.
- **A clearer creation form**: each button names its setting and pick, the form is wider and scrolls when it does not fit, and the categories picker is one checkbox per category.
- **Illustrate an X-Ray entry** from its More… menu, drawn through the image prompt writer.
- **A saved result keeps its place as a position in the text**, so an X-Ray or Recap update starts in the right spot whatever the page numbers are now. Merging section X-Rays into the main one needs the book open, unless the main X-Ray covers the whole book.
- **Automatic building pauses after a stop that would repeat**, such as a cut-off answer, a request too large or no credit, until you resume it.
- **Renaming or linking an entry holds** across checkpoint installs.
- **The name index keeps four page layouts**, so switching orientation or device no longer indexes the book again.
- **Updates in a long series send less**: only the carried names the new text mentions.
- **Every artifact list opens the same way**, with dates, and AI merge section X-Rays… where it applies.
- **Another book's X-Ray stays that book's**: its versions list acts on it, and an entry looked up from its chat does not list the open book's highlights.
- **A book whose X-Ray was deleted with its versions kept shows Archived X-Ray Versions in its Book Hub.**

### Book Groups and Cross-Book X-Ray (#116)

- **Carried entries inside the categories.** In a series, entries carried from earlier books are also listed in Cast, World, Ideas and Lexicon, after the book's own. The Carried entries setting switches back to the separate list.
- **The carried list opens by category, and Mentions lists carried names too.**
- **Possible matches finds names that changed between books**, such as a first name here and the full name carried. Link joins a pair for free, Never suggest keeps it apart, and AI merge… covers what no rule matches.
- **Every paid merge is called AI merge and says how many requests it sends**, in one "Link and merge…" group that is the same in the X-Ray popup and the browser's menu.
- **What an earlier book says about an entry this book already has is attached for free.**
- **The question before a new X-Ray in a series explains the free carry and the optional AI merge**, and the earlier book's names go with the request whatever you answer.
- **A group can set checkpoint spacing and where carried entries are listed**, on its own X-Ray screen.
- **Add one book to a group straight from the file browser.** The Group Hub's add rows name their source.
- **Moving a book or a folder in KOReader's file browser keeps its links**: groups, chats, notebooks, pinned items, pictures, scan folders and the X-Ray links other books keep to it.
- **"Add as a new entry" holds** across checkpoint installs and rebuilds.
- **A carried entry keeps what each book says about it**, in a project too.
- **The input dialog's Group button respects the series hold-back**: a later volume asks before it opens.
- **The Project description says it carries between all its books.**
- **Editing the carried list keeps your aliases in view, and a carried entry's page has a back button.**

### Chat Windows

- **The Markdown view gives every paragraph its own direction**, so a chat that mixes right-to-left and left-to-right text reads right block by block. Lists in left-to-right text are real lists again.
- **A chat about a book that is not open belongs to that book**: its title, settings and saved position. Artifacts made or regenerated from it are saved with that book.
- **Selecting a Chinese, Japanese or Korean clause in a chat window opens the selection menu** instead of a dictionary lookup.
- **A long press on the window's X closes the dictionary windows and the highlight too.**
- **Chatting about your notebook tells the AI it is your own notes.**
- **Long highlights are measured in characters, not bytes.**
- **Stopping a request before its first word stops the waiting animation**, which kept redrawing the screen.
- **A reasoning block that starts mid-answer in a streamed reply goes into the reasoning.**

### AI Book Tools

- **"Read Short Texts Whole" is a size: Off, Small, Medium (the default) or Large**, settable per book from the Tools chip's long-press.
- **A text read whole costs less in a long chat**, and a model that cannot take it searches the book instead.
- **With Book Tools Mode on Interactive, the last answer no longer fails on Claude's newest models.**

### Providers and Models

- **Claude Haiku 5.5 replaces Haiku 4.5** as Anthropic's fast model.
- **Gemini 4 Argon** joins the Gemini and OpenRouter lists as Gemini's frontier pick.
- **The OpenAI Subscription lists the GPT-6 models** (#117). Its fast pick is gpt-6-luna, which every plan serves, and a model your plan refuses says why.
- **Qwen works again**: its default is qwen3.8-max after Alibaba retired qwen3-max, its reasoning can be turned off, and AI Book Tools work on Qwen, directly and through A2Agent, OpenCode Zen and OpenCode Go.
- **OpenCode Zen works again on its default model**, now deepseek-v4.1-flash. A new workspace serves only the newer models, and Fetch models from provider... lists yours.
- **NVIDIA works again on its default model**, now nemotron-3.5-super-vl, after NVIDIA stopped serving the old one.
- **Shorter model lists**: the default and the tier picks first, then one previous version per line. A model you picked keeps working, and one the provider stopped serving moves to its replacement wherever it is stored, with a note.
- **SambaNova lists MiniMax-M3 in place of M2.7.**
- **Gemini 3 and Gemini 4 Argon requests no longer send a temperature.**
- **Claude Max and Team plans include monthly API credits that work in KOAssistant**; the wiki says how to claim them.
- **Test Connection tests the endpoint you use**, caps its request at 512 tokens and keeps its result on screen until you tap it.
- **Test provider's Reachability step reads the answer** and fails with the reason when it cannot.
- **A key saved as "your-key-here" is treated as the placeholder.**
- **A custom_models.lua prefix matches literally.**
- **Provider names read as the brands write them**: OpenAI, DeepSeek, xAI.

### Other Fixes

- **A book without a title in its metadata is named to the AI as a file name**, not as a title.
- **Two books with the same author and title no longer share one notebook.**
- **A failed request stays on screen until you tap it.**
- **Errors on the device keep their HTTP status** beside the provider's sentence.
- **`{time_since_last_read}`, used by Recap, reads KOReader's reading statistics**, and says nothing without a record.
- **The recap reminder counts from the day you really last opened the book.**
- **Redoing a Recap or another saved result of a book you are not reading starts it over** instead of reading the open book.
- **Another book's artifacts and section pages are that book's**, and Regenerate is offered only for the open book's own summary or analysis.
- **A note saved from a chat records the right book's position** and names the model that answered.
- **Browse by type lists every kind of artifact**, images, pins, section X-Rays and AI Wiki entries included.
- **The Book Hub lists section quizzes under Quiz.**
- **Counterarguments shows up with the other saved results.**
- **A section's text is sent under the section's name**, not "Full document:".
- **Domains**: Chat History's View by Domain names every domain, and Manage Domains has one Delete all custom row.
- **A book's Background note keeps its first 2,000 characters in any script**, and the editor says so.
- **A general or library action beside an open book no longer takes that book's domain, background or research mode.**
- **Research mode**: a DOI added to a book's metadata later is found, and general and library chats no longer get the research note.
- **Updates**: `auto_check_updates = false` in configuration.lua works whenever you add it, and the update checker's messages can be translated.
- **Backups**: a restore in Replace mode keeps your API keys when the backup holds none, the confirmation says what a restore point holds, and a backup skips macOS `._` files.
- **Fresh start offers the Setup Wizard when it is done.**
- **Custom reset's Behaviors & domains row clears the domains too.**
- **Quick Settings shows this book's own settings again**, and the X-Ray marking popup's reset for this book works.
- **Dictionary lookups keep spoiler protection's limit on the text after the word**, from every entry point.
- **A book chat with nothing typed asks you to type a message** instead of sending an empty one.
- **The source popup's grayed Use summary row gives its reason with every scope.**
- **In-app notices name today's menu rows**, and two messages built from fragments can be translated whole.
- **A long section X-Ray name keeps whole characters.**

### Under the Hood

- **The plugin's code moved under `koassistant/`**; your own files stay at the root. If you update by hand, delete the old folder first, after copying your files out.
- **Saved results are written whole or not at all**, so a power loss mid-write keeps the old file.
- **Artifact lists open faster** for books with many artifacts.
- **Requests name this plugin's own version**, even with another AI plugin installed.
- **Artifacts, pinned answers and AI Wiki articles record the provider that made them** and what they were built from.

### How You Can Help

- **Device reports.**
- **Translations**: review passes on [Weblate](https://hosted.weblate.org/engage/koassistant/).
- **Bug reports and feature requests.**

# v0.24.0 · 2026-10-20

# KOAssistant v0.24.0 Release Notes

KOAssistant now asks before it sends your data, a Setup Wizard checks what each update changed, pictures are written from the book and kept in a gallery, X-Rays get presets and carried entries in their categories, and the documentation moved to the wiki. The plugin's code moved into one folder, so restart KOReader right after the update.

## Highlights

- **KOAssistant asks before it sends your data.** Highlights, notes, notebook, book text, book list and reading habits are each Ask, Allow or Never, for all books, for trusted providers and per book. After the update every kind is on Ask.
- **A Setup Wizard for new installs and for updates**, and any KOReader gesture for the quick panels.
- **Pictures that match the book.** A prompt writer turns the passage, the X-Ray entries it names and your note into a picture in the style you pick, fitted to your screen; OpenRouter joins as an image provider, and a gallery keeps your pictures by book.
- **The documentation moved to the [wiki](https://github.com/zeeyado/koassistant.koplugin/wiki)**, and the README is the front door.
- **X-Ray presets, carried entries in their categories, and Possible matches** for names that changed between books.
- **Updates find their place after a font change, a turned device or a synced sidecar**, and moved books and folders keep their links.
- **New models and defaults** on Anthropic, Gemini, the OpenAI Subscription, Qwen, OpenCode Zen and NVIDIA, and new image models.
- **The plugin's code moved into one folder: restart KOReader right after the update** (on Android, close and reopen the app).

## Privacy

- **The question names the action, the provider and the amount**, and offers Allow once, Allow for this book, Not for this book and More…; your book list and reading habits offer Always allow instead. A kind set to Never is refused with a button to its setting. After the update every switch reads Ask; per-book settings and trusted providers are kept.
- **It is asked once per book, at the moment of need**: when an action starts, on the source popup's Run button, at Send with a Scope range or the Tools chip on, and when you attach or chat about your notebook. Viewing and browsing never ask.
- **One preset row: Default (Ask), Allow everything and Block everything**, in Settings → Privacy & Data → Preset. A note lists what a pick changed.
- **Book info moved to Settings → Privacy & Data, and None now means none**: nothing names the book, and actions that need the title say so instead of running.
- **Book Settings → Privacy & Data shows the book's values and the global ones on two tabs**, and the Quick Settings tile of the same name opens it.
- **Groups can hold privacy values** for every member, in Group Settings → Privacy & Data. A group's Never works like a book's.
- **Trusted providers have their own column of values**, Allow by default, under Settings → Privacy & Data → What trusted providers may use.
- **The text around what you tap is its own kind of data**, allowed by default: the context of a highlight or a lookup, the current page, the text around an image's passage. Set to Never, it is now kept out everywhere.
- **Automatic X-Ray asks once per book** before it builds, and a build you start by hand asks once for all its checkpoints.
- **Saved results follow what they were built from.** Chatting about an artifact, attaching one, or the AI Wiki asks for those kinds, and is refused when one is Never for the book.
- **AI merges ask once before their requests, and the free carry between a group's books works on Ask**; only a book set to Never stays out.
- **A chat remembers what it was given** and checks it again when you continue it, or continue it with another provider.
- **Delete Book Artifacts left the privacy screen.** A book's artifacts are deleted from its Book Hub or the artifact browser.
- **An X-Ray entry page lists your matching highlights whatever the highlights value**, since they stay on the device until you chat about the entry.
- **Rows and chips that need a kind on Ask are offered**, not grayed out; only Never grays them.
- **The note above an answer made without some data says why**, in your language.
- **Every privacy check judges the provider the request really goes to**, a model picked by holding Send or by the Quick preset included, and an action on a closed book checks that book's own settings.
- **Updating an artifact whose action does not use book text sends no new text.**
- **Attachments ride chats and plain actions only**, never an action that saves a result, nor the dictionary and translate actions.

## Actions and Menus

- **The Setup Wizard has two faces.** A fresh install gets the welcome chain: provider, privacy, language, icons and font, the (KOA) mark, gestures. After an update it checks only what the version changed, and Settings → Setup Wizard re-runs any step.
- **Any KOReader gesture for the quick panels and gesture actions**, from Settings → Gestures or the wizard. A gesture in use can be replaced.
- **The emoji font installs from Settings** (Display Settings → Emoji → Emoji Font), with a display test that turns the icons on.
- **Run an action once without the book info, or with it**, from its long-press menu. In a book chat, the gear menu's Send book info switches it for that chat.
- **Quick is clearer.** Each action's editor has a Takes the Quick preset box that decides whether Quick reaches it, the buttons that take Quick carry a ⚡ mark, and Quick's Book tools off reaches Explain in Context.
- **The scope popup follows the chat's Spoiler chip** for that run.
- **The (🔍) mark shows whenever an action could search the book**, not only with the book's text on Allow and the Tools chip on.
- **+Vocab stores the word as KOReader does**, and no longer says Added while the Vocabulary builder is off.
- **"Compare with KOAssistant" shows in the file browser's selection menu in every language.**
- **The sample custom actions file loads again**, and an action with an unknown context is skipped with a log line.
- **The long-press menu no longer offers Duplicate for X-Ray.**
- **Placeholders**: the surrounding-context placeholder in your own actions always brings the context, a placeholder with nothing behind it is dropped instead of sent as written, and a book action from the file browser can read your library list again.

## Image Generation

- **The image prompt writer.** Your chat provider's fast model writes the prompt from the passage, the text around it, the X-Ray entries it names and your note. The privacy question names both providers, and Write the prompt with AI turns it off.
- **A style for every picture**: Book illustration, Watercolor, Ink drawing, Pencil sketch, Woodcut, Photographic, Comic, Map or diagram, or your own words.
- **A note for one picture**: long-press Generate Image for Generate with a note…, or type it in the highlight input dialog.
- **One Shape and one Detail setting for every image provider.** Shape fits your screen by default, and Detail starts at Draft, the fastest and cheapest.
- **New image models**: GPT Image 2.5 flare as OpenAI's default, Nano Banana 2.1 on Gemini, Grok Imagine Image 2.0 on xAI.
- **OpenRouter makes images too**: GPT Image 2.5 Flare, Nano Banana 2.1, FLUX 3, Seedream and Recraft, and its whole image catalog under More models….
- **Generate Image shows whenever you have a key for an image provider**, and the first tap asks which one draws when your chat provider cannot.
- **A thumbnail gallery, by book.** Long-press a picture to draw it again, edit its prompt or delete it.
- **Image settings on the spot**: long-press Generate Image, or a picture in the gallery. Regenerate draws in the style now in effect, and Regenerate and replace swaps the old picture.
- **Gemini's Draft pictures come faster**: about 9 seconds instead of 13 to 23.
- **Image prompts follow chat's rules** for Book info, Context Direction and spoiler protection.
- **Clearer refusals and real file types**: a refusal names the provider's reason, Gemini image requests follow Gemini Content Filter, and Gemini's and xAI's pictures are saved as .jpg.
- **The image settings follow the provider that makes the images**, and a slow picture gets three minutes.

## X-Ray

- **Presets for new X-Rays**, from Characters only to Deep study, in the creation form, Book Settings, Group Settings and Settings.
- **"Where things stand" can be turned off** in the categories picker, which makes updates shorter.
- **A clearer creation form**: each button names its setting and pick, the form is wider and scrolls when it does not fit, and the categories picker is one checkbox per category.
- **Illustrate an X-Ray entry** from its More… menu, drawn through the image prompt writer.
- **A saved result keeps its place as a position in the text**, so an X-Ray or Recap update starts in the right spot whatever the page numbers are now. Merging section X-Rays into the main one needs the book open, unless the main X-Ray covers the whole book.
- **Automatic building pauses after a stop that would repeat**, such as a cut-off answer, a request too large or no credit, until you resume it.
- **Renaming or linking an entry holds** across checkpoint installs.
- **The name index keeps four page layouts**, so switching orientation or device no longer indexes the book again.
- **Updates in a long series send less**: only the carried names the new text mentions.
- **Every artifact list opens the same way**, with dates, and AI merge section X-Rays… where it applies.
- **Another book's X-Ray stays that book's**: its versions list acts on it, and an entry looked up from its chat does not list the open book's highlights.
- **A book whose X-Ray was deleted with its versions kept shows Archived X-Ray Versions in its Book Hub.**

## Book Groups and Cross-Book X-Ray (#116)

- **Carried entries inside the categories.** In a series, entries carried from earlier books are also listed in Cast, World, Ideas and Lexicon, after the book's own. The Carried entries setting switches back to the separate list.
- **The carried list opens by category, and Mentions lists carried names too.**
- **Possible matches finds names that changed between books**, such as a first name here and the full name carried. Link joins a pair for free, Never suggest keeps it apart, and AI merge… covers what no rule matches.
- **Every paid merge is called AI merge and says how many requests it sends**, in one "Link and merge…" group that is the same in the X-Ray popup and the browser's menu.
- **What an earlier book says about an entry this book already has is attached for free.**
- **The question before a new X-Ray in a series explains the free carry and the optional AI merge**, and the earlier book's names go with the request whatever you answer.
- **A group can set checkpoint spacing and where carried entries are listed**, on its own X-Ray screen.
- **Add one book to a group straight from the file browser.** The Group Hub's add rows name their source.
- **Moving a book or a folder in KOReader's file browser keeps its links**: groups, chats, notebooks, pinned items, pictures, scan folders and the X-Ray links other books keep to it.
- **"Add as a new entry" holds** across checkpoint installs and rebuilds.
- **A carried entry keeps what each book says about it**, in a project too.
- **The input dialog's Group button respects the series hold-back**: a later volume asks before it opens.
- **The Project description says it carries between all its books.**
- **Editing the carried list keeps your aliases in view, and a carried entry's page has a back button.**

## Chat Windows

- **The Markdown view gives every paragraph its own direction**, so a chat that mixes right-to-left and left-to-right text reads right block by block. Lists in left-to-right text are real lists again.
- **A chat about a book that is not open belongs to that book**: its title, settings and saved position. Artifacts made or regenerated from it are saved with that book.
- **Selecting a Chinese, Japanese or Korean clause in a chat window opens the selection menu** instead of a dictionary lookup.
- **A long press on the window's X closes the dictionary windows and the highlight too.**
- **Chatting about your notebook tells the AI it is your own notes.**
- **Long highlights are measured in characters, not bytes.**
- **Stopping a request before its first word stops the waiting animation**, which kept redrawing the screen.
- **A reasoning block that starts mid-answer in a streamed reply goes into the reasoning.**

## AI Book Tools

- **"Read Short Texts Whole" is a size: Off, Small, Medium (the default) or Large**, settable per book from the Tools chip's long-press.
- **A text read whole costs less in a long chat**, and a model that cannot take it searches the book instead.
- **With Book Tools Mode on Interactive, the last answer no longer fails on Claude's newest models.**

## Providers and Models

- **Claude Haiku 5.5 replaces Haiku 4.5** as Anthropic's fast model.
- **Gemini 4 Argon** joins the Gemini and OpenRouter lists as Gemini's frontier pick.
- **The OpenAI Subscription lists the GPT-6 models** (#117). Its fast pick is gpt-6-luna, which every plan serves, and a model your plan refuses says why.
- **Qwen works again**: its default is qwen3.8-max after Alibaba retired qwen3-max, its reasoning can be turned off, and AI Book Tools work on Qwen, directly and through A2Agent, OpenCode Zen and OpenCode Go.
- **OpenCode Zen works again on its default model**, now deepseek-v4.1-flash. A new workspace serves only the newer models, and Fetch models from provider... lists yours.
- **NVIDIA works again on its default model**, now nemotron-3.5-super-vl, after NVIDIA stopped serving the old one.
- **Shorter model lists**: the default and the tier picks first, then one previous version per line. A model you picked keeps working, and one the provider stopped serving moves to its replacement wherever it is stored, with a note.
- **SambaNova lists MiniMax-M3 in place of M2.7.**
- **Gemini 3 and Gemini 4 Argon requests no longer send a temperature.**
- **Claude Max and Team plans include monthly API credits that work in KOAssistant**; the wiki says how to claim them.
- **Test Connection tests the endpoint you use**, caps its request at 512 tokens and keeps its result on screen until you tap it.
- **Test provider's Reachability step reads the answer** and fails with the reason when it cannot.
- **A key saved as "your-key-here" is treated as the placeholder.**
- **A custom_models.lua prefix matches literally.**
- **Provider names read as the brands write them**: OpenAI, DeepSeek, xAI.

## Other Fixes

- **A book without a title in its metadata is named to the AI as a file name**, not as a title.
- **Two books with the same author and title no longer share one notebook.**
- **A failed request stays on screen until you tap it.**
- **Errors on the device keep their HTTP status** beside the provider's sentence.
- **`{time_since_last_read}`, used by Recap, reads KOReader's reading statistics**, and says nothing without a record.
- **The recap reminder counts from the day you really last opened the book.**
- **Redoing a Recap or another saved result of a book you are not reading starts it over** instead of reading the open book.
- **Another book's artifacts and section pages are that book's**, and Regenerate is offered only for the open book's own summary or analysis.
- **A note saved from a chat records the right book's position** and names the model that answered.
- **Browse by type lists every kind of artifact**, images, pins, section X-Rays and AI Wiki entries included.
- **The Book Hub lists section quizzes under Quiz.**
- **Counterarguments shows up with the other saved results.**
- **A section's text is sent under the section's name**, not "Full document:".
- **Domains**: Chat History's View by Domain names every domain, and Manage Domains has one Delete all custom row.
- **A book's Background note keeps its first 2,000 characters in any script**, and the editor says so.
- **A general or library action beside an open book no longer takes that book's domain, background or research mode.**
- **Research mode**: a DOI added to a book's metadata later is found, and general and library chats no longer get the research note.
- **Updates**: `auto_check_updates = false` in configuration.lua works whenever you add it, and the update checker's messages can be translated.
- **Backups**: a restore in Replace mode keeps your API keys when the backup holds none, the confirmation says what a restore point holds, and a backup skips macOS `._` files.
- **Fresh start offers the Setup Wizard when it is done.**
- **Custom reset's Behaviors & domains row clears the domains too.**
- **Quick Settings shows this book's own settings again**, and the X-Ray marking popup's reset for this book works.
- **Dictionary lookups keep spoiler protection's limit on the text after the word**, from every entry point.
- **A book chat with nothing typed asks you to type a message** instead of sending an empty one.
- **The source popup's grayed Use summary row gives its reason with every scope.**
- **In-app notices name today's menu rows**, and two messages built from fragments can be translated whole.
- **A long section X-Ray name keeps whole characters.**

## Under the Hood

- **The plugin's code moved under `koassistant/`**; your own files stay at the root. If you update by hand, delete the old folder first, after copying your files out.
- **Saved results are written whole or not at all**, so a power loss mid-write keeps the old file.
- **Artifact lists open faster** for books with many artifacts.
- **Requests name this plugin's own version**, even with another AI plugin installed.
- **Artifacts, pinned answers and AI Wiki articles record the provider that made them** and what they were built from.

## How You Can Help

- **Device reports.**
- **Translations**: review passes on [Weblate](https://hosted.weblate.org/engage/koassistant/).
- **Bug reports and feature requests.**

# v0.23.0 · 2026-09-30

# KOAssistant v0.23.0 Release Notes

Run any action with another model in one long-press, X-Ray marking and book search that no longer stall large books on e-readers, Perplexity on its new API, a new provider and a round of new models, and many fixes. 

## Highlights

- **Run an action once with another model, or switch models from the highlight menu (#86).** Long-press any action button for Quick answer, your favorite and recent models, No reasoning, web search on or off. The highlight menu's first KOAssistant button shows your model and switches it.
- **X-Ray underlines no longer freeze the reader**, and Chapter Appearances and Mentions open at once from a name index kept next to the book.
- **Perplexity moves to its new Agent API**, with Sonar and other companies' models on one key; the old API was ended on 2026-09-27.
- **AI Book Tools search long books without stalling**, read short texts whole, and search Japanese, Chinese, Korean, Arabic and other scripts properly.
- **X-Ray builds are steadier:** they survive the device sleeping, respect hidden sections, skip front matter, resume where they stopped, and you can set a book's X-Ray type (Fiction, Nonfiction, Academic).
- **New provider A2Agent (#108)** and new models on most providers: Claude Sonnet 5.5, Opus 5.5 and Fable 5.1, GPT-6 and GPT-6.1, Gemini 3.8 Flash, Grok 4.7, GLM-5.3, Kimi K3 and more, with new defaults on Anthropic, OpenRouter, Gemini and xAI.
- **Fixes that mattered:** backups on e-readers (#110), a Mac-copied install that failed every action (#112), an empty reply closing KOReader (#111), Kimi and regional servers, and updates that check the download before installing.

## Models and Run Options

- **Run an action once another way.** Long-press an action button (highlight menu, dictionary popup, Quick Actions, input dialogs, file browser): the menu opens with Quick answer, up to three models (favorites, then recent picks, then your provider's fast model), No reasoning, with or without web search, and More models… for any model you have a key for. The action runs that one time with your pick; your settings do not change. An action's own settings still hold, but a model you pick beats even a model pinned on the action. Artifact actions (X-Ray, summaries, recaps, the quiz, AI Wiki) carry the pick through their popup to the run you start there; checkpoint builds and automatic updates keep your default model. The chat that opens stays on the picked model, also when you resume it later. Below a double line sit the rows that change the action for good: Add to or Remove from that menu, Edit… and More….
- **Favorite models.** Long-press a model in any model list to add it to your favorites; ♥ marks them (★ still marks a custom model). Favorites take the first model buttons of every long-press menu and lead the More models… list.
- **Send with another model.** Long-press Send in an input dialog, the reply window or when starting a chat about an artifact: your model buttons, No reasoning and More models…. The pick applies to that message and the rest of the chat.
- **Switch your model from the highlight menu (#86).** The highlight menu's first KOAssistant button shows your model; tap it for favorites, recent picks or More models…, and the model changes for everything after while the menu and your selection stay open. It is the **Switch model** entry of Settings ▸ Menus & Buttons ▸ Highlight Menu Actions; Dictionary Popup Actions can add it to the dictionary popup.
- **Your model in the input dialog's gear menu**, with the same list; a pick changes your model and the dialog reopens on it.
- **Model lists open on the model you use** instead of the first page, in Settings and in AI Quick Settings.
- **The model list's tier tags follow your own tier picks** ("· fast", "· ultrafast").

## X-Ray

- **Underlines no longer freeze the reader.** Passive marking searched the whole book for each name on the reader's thread (seconds per name on an e-reader, minutes for an Arabic name), which could stall pages until Android closed KOReader. Marks are now found on the page you are on, after it settles, at the same cost on any size of book. They land on the right words with soft hyphens and Japanese furigana.
- **Chapter Appearances and Mentions open at once.** Where each name appears is found once, in the background, and kept next to the book (seconds for a novel, a minute or two for a collected works on an e-reader). New names and aliases are added on their own; a font or margin change indexes again for the new layout. Opened before the index is ready, Chapter Appearances searches right then, with a message you can tap to cancel. A section X-Ray opens on its own pages at once.
- **"After 10/25 unseen pages" and "First appearance only" are exact** now that they read the name index; until the index is ready, a name is marked once per page.
- **One way of counting everywhere.** Chapter Appearances counts whole names, as Mentions and the underlines always did ("Ann" no longer counts inside "Annual"). A bracketed part of a name counts as a name only when it is the name in another script ("Tokyo (東京)"), not a label like "(archetype)". A leading "The" is optional while two words remain. Whole-book Mentions no longer stops after the first 5 MB of text. Chinese, Japanese, Korean and Arabic names are underlined and counted like the rest.
- **Arabic names no longer match inside other words.** They match at the start of a word or after its prefixes (و, ف, ب, ك, س, ل, the article), with at most three letters after; a word's first alef is required, and a name needs three letters. Each book's index is rebuilt once for the rule. The X-Ray instructions also say aliases are names, never pronouns.
- **Tapping an underlined name opens its card when the name has a part in brackets**, and a name in another script inside the brackets finds it too.
- **X-Ray cards say when an entry comes from a section X-Ray** ("From the section X-Ray:" and the section's name). "Marking & lookup…" names what marks and lookups read (this book's X-Ray, its section X-Rays, the other books in its group) and is offered for books with only section or group X-Rays too.
- **Choose an X-Ray's type.** "New X-Ray type" in Book Settings ▸ X-Ray picks Fiction, Nonfiction or Academic (for every book: Settings ▸ Reading & Library ▸ X-Ray ▸ Type of New X-Rays; groups can set it). Auto, the default, lets the AI decide. A set type sends that schema alone, so the request is smaller. The creation form shows the type, and picking a type a book's X-Ray does not have offers a rebuild. Updates keep an X-Ray's type.
- **Fiction is no longer typed as nonfiction because of its introduction.** The AI judges the work itself (a known title and author, otherwise the main text), never an editor's introduction or a chronology. New X-Rays also see the table of contents of the text they receive. A very small model can still be misled when the first checkpoint ends inside the introduction; "New X-Ray type" sets it right with a rebuild.
- **A checkpoint with nothing to build from is skipped.** In an annotated edition the first checkpoint may hold only front matter; an empty step is skipped and the next reads further, at most three times and never past half the book, after which the build stops with "nothing to build from so far". Section X-Rays are built whatever the section holds.
- **The checkpoint introduction is an introduction again.** Since v0.22.1 it came out as a full X-Ray of the first stretch whenever the default categories applied, and the first checkpoint was built on top of it. It covers the premise, the setting and the first characters again.
- **Checkpoints in books with hidden sections.** Checkpoint positions and section targets now count the visible pages, as your reading position does, so builds no longer fall into text hidden with KOReader's hidden flows, and a step that would send no book text stops the build and says so.
- **Checkpoints carry on after the device sleeps.** On e-readers where KOReader turns Wi-Fi off for sleep, a request in flight stops, the popup says the build is waiting for Wi-Fi, and the checkpoint is built again seconds after Wi-Fi reconnects. Checkpoints already built keep installing meanwhile.
- **A stopped build tells you, and resumes in one tap.** The notice stays until you close it, with a Resume button; a step that fails for a passing reason is tried twice first. Resume continues the build that stopped (to your position, to a section's end, or as one request) rather than planning to the end of the book, and is not offered after a build that found nothing to build from.
- **A rebuild works like a new X-Ray.** It starts with the same introduction, and your current X-Ray stays until that first part is saved, so a rebuild cancelled or failed before then changes nothing. Each step counts only what it saved itself.
- **Section X-Rays follow your X-Ray settings** (the categories, depth and type of Book Settings ▸ X-Ray or the global X-Ray settings) instead of every category at standard depth.
- **A cut-off answer is never passed off as done.** An answer cut at its length limit or ended early by the provider is not saved, and you now see it marked as cut off instead of the old saved copy (an X-Ray update no longer opens your old X-Ray as if it had worked, nor a Recap update the old Recap). "X-Ray not saved" says what helps: a lighter depth or fewer categories, updating in checkpoints, or a model that allows longer answers. When the AI declines an X-Ray, you see its answer instead of the X-Ray already on the device.
- **X-Ray popups update while open** (build progress, the Wi-Fi wait, background updates), and the popup names the checkpoint being built ("The next checkpoint (20%) is being built and installs when you reach it.").
- **Smaller fixes:** the duplicate-entries question waits for a checkpoint build to finish; Extend and Rebuild stay in the popup after a cancelled automatic build; "Resume building checkpoints" no longer appears while Automatic X-Ray is on; a tap outside the large-request question counts as Cancel instead of leaving the build waiting.

## Book Groups and Cross-Book X-Ray (#90)

- **One carried entry per character**, even when earlier books name them differently (a short name in one volume, the full name in the next): the carried list shows one row, with the other volume's description as a "From earlier books" line. A carried entry's full view opens with its description; the "Not seen in this book yet" note closes it.
- **Japanese names keep their middle dot.** Models that write "_" or "-" for "・" split one character into two entries; names, aliases and carried entries are repaired when read, and the duplicate review and search treat the spellings as one.
- **Underlines no longer vanish** when a character is known under two names across a series; each name paints once.
- **Look up in X-Ray ignores a stop or bracket the selection dragged along** in Japanese or Chinese text.
- **Fixed a crash** when a search hit a carried entry from a book with a long title; the title is shortened beside the name.

## AI Book Tools

- **Long books no longer freeze the reader.** Search asks KOReader's own document search for the pages worth reading, in a background process a tap on Stop cancels, instead of copying the whole text on every question (minutes, and more memory than an e-reader has, on a 6,000-page collected works). Typo-tolerant matching is gone; the AI retries a spelling instead.
- **Short texts are read whole.** When the readable text fits (about 64,000 characters at Quick and Standard effort, 128,000 at Thorough) the AI gets it in one piece instead of search snippets, and the usage line reads "Book text read in full". Toggle "AI Book Tools: Read Short Texts Whole" in Settings ▸ Advanced, on by default.
- **Better hits.** The 12 best hits per query (up to 40 on request), spread over pages, with exact totals; whole-word hits rank above hits inside longer words; sentences holding most words of a longer query are listed below full matches with the missing words named; very common words (decided from the book itself) are not required; a small word index built at the first lookup serves the rest of the request.
- **Every script.** Japanese, Chinese and Korean queries match literally; Arabic, Hebrew, Cyrillic, Greek and accented words are words (any order, the partial rule, case folded); Chinese, Japanese and Arabic sentence marks end sentences.
- **Book text language.** New setting "Tell the AI the Book's Language" (Settings ▸ AI Language Settings, off by default): set to "From the book's metadata", book-tool sessions name the language the text is in, so an English question about an Arabic novel gets Arabic searches. Book Settings ▸ Languages and group settings gain a "Book text language" row (Follow global, Off, From metadata, a listed or typed language). The model is also told to write queries in the text's language.
- **A smarter table of contents tool.** Exact entry counts, narrowing to the top level or to titles containing a phrase (each with its parent chapters), and when the list is too long the chapter levels that fit are kept rather than the first entries. Before its first lookup the model sees a short outline of the contents and its lookup budget in lookups and rounds.
- **Honest results.** Tool results say what they left out (caps, cut passages, pages out of reach because of spoiler protection or hidden sections), and the model is told to pass that on. An answer given without a lookup says the book was not consulted. Sources and Lookups lists the pages where each query hit, and the filters behind a "toc: 0 entries" line.
- **Fewer caveats.** Answers no longer end with a paragraph about hit counts and partial matches; a limit is mentioned in one sentence, only when part of the book was out of reach.

## Providers and Models

- **Perplexity moves to its new Agent API.** Perplexity ended the API older versions use (Sonar chat completions) on 2026-09-27; once it is switched off, every Perplexity request on an older version fails. Perplexity now serves Sonar and other companies' models on the same key: the list holds Sonar (the default), GPT-6 Luna, GPT-6 Sol, Claude Sonnet 5.5, Gemini 3.8 Flash and Grok 4.7, and Fetch models lists the rest. With web search on, the model answers through Perplexity's search with numbered citations, as in Perplexity's app; off, it answers without a search. Old Sonar model names move to Sonar with a one-time note. Sources shows only the cited sources; Show Sources lists everything found. Test provider is not offered for Perplexity; Settings ▸ Advanced ▸ Test Connection checks it.
- **New provider: A2Agent (#108).** A paid gateway to DeepSeek, GLM, Kimi, Qwen and MiniMax behind one key (Tools ▸ KOAssistant ▸ API Keys & Auth, or `a2agent` in apikeys.lua). Reasoning follows each model's settings; GLM models always reason. Book tools work on its DeepSeek, GLM, Kimi and MiniMax models.
- **New models**, each tested against its provider's API: Claude Sonnet 5.5, Opus 5.5 and Fable 5.1; GPT-6 Sol, Luna and Astra, and GPT-6.1 Sol; Gemini 3.8 Flash; Grok 4.7; GLM-5.3, 5.3 Flash and 5.3 FlashX; Kimi K3; Qwen 3.8 Max, Flash and 27B; MiniMax M3; DeepSeek V4.1 Flash on Fireworks; and the same models on OpenRouter, Requesty, Perplexity, Groq and Fireworks where they serve them. GPT-6 models reason by default; GPT-6 Astra, GPT-6.1 Sol, Claude Opus 5.5 and GLM-5.3 cannot turn reasoning off, so Minimal and the Quick chip give them their lowest level; Claude Sonnet 5.5's Off sends Anthropic's lowest setting, which does not think on ordinary questions. GPT-6.1 Sol is OpenAI's Flagship-tier model.
- **New default models.** Anthropic and OpenRouter start on Claude Sonnet 5.5 (same price as Sonnet 5), Gemini on Gemini 3.8 Flash (same price as 3.7 Flash), xAI on Grok 4.7 (cheaper than 4.6), DeepSeek on deepseek-flash (V4 Pro stays in the list and the flagship tier), Together on DeepSeek V4 Pro 0813 (from its catalog, untested). If you never picked a model you move at the next start, with a one-time note; a picked model stays. The tiers point at the new models: Claude Opus 5.5, GPT-6.1 Sol, Grok 4.7 and GLM-5.3 flagship; Claude Fable 5.1 and GPT-6 Astra frontier; Claude Sonnet 5.5 and Gemini 3.8 Flash standard.
- **Retired models are replaced.** NVIDIA (Nemotron 3 Nano, gpt-oss-120b, MiniMax M3), Groq (Compound, Compound Mini), Fireworks (DeepSeek V4 Pro and V4 Flash 0731, Kimi K2.6, gpt-oss-20b, GLM-5.2), OpenCode Go (GLM-5.1, GLM-5, MiniMax M2.5, Qwen 3.7 Max, 3.6 Plus, 3.5 Plus, Kimi K2.6) and OpenCode Zen (GLM-5, Kimi K2.6 and K2.5, DeepSeek V4 Flash Vision, the free Nemotron) stopped serving these; a saved pick moves to a replacement with a one-time note, and tiered actions use models that answer. No NVIDIA model offers book tools any more.
- **Kimi chats work again.** Since v0.21.0 kimi-k2.6 refused every chat over its temperature; it now gets temperature 1 while it thinks and none when reasoning is off. Forced values under `constraints` in custom_models.lua now apply to every provider.
- **Z.AI, Qwen and Kimi use the region you set.** The Region setting had no effect, so keys from the China or US platforms were refused. If one of these stops working after this update, set its region to the platform that issued your key.
- **X-Rays work on Cohere**, and so do Command R7B and Command A: KOAssistant knows each model's output limit and retries once at the limit Cohere names.
- **Reasoning fixes.** Grok 4.5 and Grok 4.20 Reasoning at Minimal work (the lowest level, or no setting on a model that always reasons); turning reasoning off works on Fireworks (GLM-5.3 and gpt-oss get their lowest level there); Claude Fable 5, Grok 4.6 and gpt-oss through OpenRouter, and Claude Fable 5, Sonnet 5.5 and Opus 5.5 through Requesty, get their lowest level at Minimal instead of a refused off; reasoning from models that end their thinking with a bare `</think>` (Qwen3 Thinking, DeepSeek R1 on some hosts) goes to the reasoning view instead of the answer.
- **Book tools work on Claude Sonnet 5.5, Opus 5.5 and Fable 5.1**, on Anthropic and through OpenRouter: they refuse a forced lookup, so they are asked without the force.
- **Test provider tests the requests KOAssistant really sends.** Each step is built like a real request (route, region, thinking off for tool steps), so it no longer fails where nothing is wrong, and a failed step shows the provider's explanation. It is offered for OpenAI-style providers; the others have Settings ▸ Advanced ▸ Test Connection.
- **Also:** Qwen at temperature 2.0 works (1.9 is sent); longer answers on NVIDIA (16,384 tokens) and on OpenRouter's GPT-6 (32,768); custom providers and hand-typed model ids ignore stray spaces once saved again.

## Chat Windows

- **Dictionary lookups can show the word in its sentence.** Settings ▸ Dictionary Settings ▸ Show Excerpt (off by default, also on the gear menu of dictionary windows) opens the answer with a short excerpt around the word, the word in bold. It needs Ctx on; nothing extra is sent.
- **The compact dictionary popup grows to fit a long answer**, from 60% of the screen up to 80%, and rotating the device no longer snaps it to full height. Its Expand button is now → Chat, one tap to the full chat; actions set to the full-size dictionary view (Deep Analysis) still open in it.
- **Translate and artifact windows fit their text** as laid out, without a band of empty space at the bottom.
- **A long Quick Explain answer opens the normal chat window** instead of the compact dictionary window.
- **The dictionary bypass works in artifact windows** (a book's About from the file browser, AI Wiki entries, pinned answers, X-Ray versions).
- **Smaller fixes:** no reasoning line in dictionary windows (Show Reasoning still has it); the response window names the action while an answer streams; the reply window's ⚡ chip reads ON or OFF instead of "SET".

## Actions and Menus

- **Book passages and an attached notebook go only where your privacy settings allow.** Both are now checked against the provider that receives the request (the Quick preset's model, or a one-run pick), and left out with a notice where book text or notebook sharing is not allowed for it.
- **X-Ray (Simple) is a button in the input dialog of a book that is not open** (a long-press in the file browser); it was the one action behind Show More Actions… there.
- **Quick Settings and Quick Actions** are the first rows of Tools ▸ KOAssistant, for readers without a gesture for them.
- **The "(KOA)" mark can be turned off** per surface in Settings ▸ Menus & Buttons (highlight menu, dictionary popup, file browser).
- **Fixes:** switching actions in the compact window no longer keeps the last action's model; the action wizard no longer leaves a second settings screen behind; "+ Dict. Popup" on an action's details screen says "Added"; Generate Image no longer shows the web search icon; dictionary lookups in PDF and DjVu get the plain word (no trailing punctuation or "'s"), as KOReader's dictionary does.

## Backups and Updates

- **Backups work on e-readers again (#110).** "Create Backup" reported success with 0 B and an empty folder on every e-reader; backups are written for real, a failing backup says so, and a restore makes its restore point again.
- **A failed restore can undo itself again**; the rollback no longer waits on a lock the restore holds.
- **Safer updates.** Update Now checks the download against the release's size and checksum, so a cut or damaged download never replaces your plugin; slow Wi-Fi gets up to 10 minutes; your files are checked before anything is deleted, and a file that cannot be carried over keeps the old folder and tells you where it is; a linked `domains/` or `behaviors/` folder keeps its files; a git checkout is never replaced. These protect the update after this one: an update always runs the updater you already have.
- **No more "Don't warn again"** on the large-text and cut-text warnings; they offer Cancel or Continue, and Settings ▸ Privacy & Data ▸ Text Extraction turns one off.

## Other Fixes

- **Actions no longer fail with "there was an error parsing the body" (#112).** A plugin copied from a Mac carries hidden companion files next to every file; one next to a behavior or domain file could be loaded as the AI's instructions, and the provider then refused every request (only Dictionary, Quick Definition and Translate worked). Those files are ignored, a damaged behavior or domain falls back to the built-in one, and every request is checked and repaired before it is sent. The same fix covers text cut mid-character in Japanese, Chinese, Korean and other multi-byte books, for X-Ray chapters, book-tool results and the long-text notice.
- **An empty reply from a provider no longer closes KOReader (#111).** You get "Empty response from <provider>. Please try again."; a reply the plugin cannot read ends in a message too; a checkpoint run tries that checkpoint again, up to twice, before stopping.
- **A tap outside a step goes back one step**, everywhere a screen closes to open the next: the X-Ray creation form's lists, checkpoint and version cards, section X-Ray options, Marking & lookup, Merge from another book, the duplicates list, the alias picker, a group's "Move to position", a book's Groups screen, the Quiz numbers, the action wizard and editors. A tap outside does what Back or Cancel does.
- **The note about a changed model names KOAssistant**, so it no longer appears out of nowhere.
- **Translations.** This release's 94 new strings are machine-translated in all 26 languages (marked for review on Weblate), and labels keep their edge spaces: prefixes such as "Provider:" and suffixes such as "(book)" had lost the space that joins them to a value, so a German screen read "Anbieter:Anthropic". About 50 labels per language are repaired, and the translation tooling keeps the spaces from now on.

## How You Can Help

- **Device reports.**
- **Translations**: review passes on [Weblate](https://hosted.weblate.org/engage/koassistant/).
- **Bug reports and feature requests.**

# v0.22.1 · 2026-09-07

# KOAssistant v0.22.1 Release Notes

Maintenance release for v0.22.0: two small fixes and one changed default. Notes for v0.22.0 below, since they came in quick succession.

## Maintenance (v0.22.1)

- **New X-Rays default to the Reference preset** (characters, places, themes and terms; no timeline or argument development) instead of all categories. Builds finish noticeably faster on every model, everything you can tap on in the book is still tracked, and Recap covers what happened. Pick All categories under Settings > X-Ray > Categories for New X-Rays (or per book) to get the timeline back. Existing X-Rays keep the categories they were built with. Note: if you had picked All categories globally before this version, that pick was stored as "no preference" and now reads as Reference; pick All categories once more to restore it.
- **Group Hub and Book Hub show real titles and authors for books you have never opened.** They used to fall back to the file name with no author until the book was opened once. The book picker's collection and folder lists do the same when KOReader's cover browser has already cached the metadata.
- **The KOAssistant row now sits at the top of the Tools menu**, in both the reader and the file browser, instead of at the very end after "More tools".

---

# KOAssistant v0.22.0 Release Notes

> **SHIPPED 2026-09-07** as tag `v0.22.0` (108 commits since v0.21.2). The GitHub release body is this file minus the trailer; the recipe is [release_recipe.md](release_recipe.md).

> **Behavior changed in this release.** Nothing starts a book's X-Ray on its own any more, and every first build asks first. Three settings were removed with that change: "Also Start X-Rays Automatically", "First Build for New Books" and "Offer Automatic X-Ray for New Books". If you had them on, see the first two bullets below. Existing X-Rays, chats, notebooks and API keys are not affected.

> **Your per-book data moved.** Chats and per-book settings now live in the book's own `.sdr` folder in plugin files instead of inside KOReader's `metadata.lua`. The move happens automatically on first start and nothing is lost; details under Storage.

---

## Spoiler Protection and X-Ray

**Automation only continues what you started.**

- **Nothing starts an X-Ray on its own.** "Automatic X-Ray (all books)" now only keeps up to date the X-Rays you have already started; a book with no X-Ray is left alone. The settings that used to start one ("Also Start X-Rays Automatically", "First Build for New Books" and its coverage question, "Offer Automatic X-Ray for New Books") are gone. Stale values are ignored, nothing needs migrating.
- **Every first build asks first.** The two ways to start a background X-Ray are the creation form's "In checkpoints, as I read (automatic)" pick and the per-book "Automatic X-Ray: On" switch. Both now say how many background requests they need right now and wait for **Start**; **Cancel** puts the switch back the way it was and nothing runs. (When nothing needs building right now, the switch just turns on.) A book left On while it was closed gets the same question the moment the first build would start, with "Cancel (turn Automatic X-Ray off)" as the way out. Books that already have an X-Ray keep being extended silently, which is what Automatic means.
- **Deleting an X-Ray now quiets automation for that book**, so nothing re-asks or restarts behind you after a delete.
- The Automatic X-Ray cooldown is cleared when a build chain finishes; a completed chain used to silently decline page-turn triggers for a whole cooldown.

**New: depth.**

- **Depth of New X-Rays: Light / Standard / Deep.** Light is one line per entry and only recurring figures and turning points; Standard (the default, unchanged from before) is a few sentences per entry; Deep is longer entries with richer connections. Set the default in **Settings > Reading & Library > X-Ray > Depth of New X-Rays**, per book in **Book Settings > X-Ray > New X-Ray depth**, or from the creation form. It applies to creates and rebuilds; checkpoints and updates keep the depth the X-Ray was started with.

**Categories.**

- **Presets renamed and re-cut**: **All categories**, **Characters and story (people, timeline)**, **Reference (everything except the timeline)**, **Characters only**. The timeline turned out to be the single heaviest block of an X-Ray, so "Reference" is now the cheap pick and cost lives on the depth dial instead. The picker separates presets from picking categories one by one.

**Creation form and checkpoints.**

- Spacing, categories and depth sit on one small options row above the action buttons, each button showing its current value, and the categories and depth pickers open on the book tab from there and from Book Settings. On a plain extend the categories and depth buttons show what the X-Ray was started with (they are locked to it), not the current default.
- A one-step checkpoint plan stays pickable instead of disappearing, and the 100%-covered "Rebuild X-Ray..." row opens the rebuild form directly (no more deleting first).
- A build that only covers up to your position no longer spends a request on a separate introduction it would immediately supersede.
- The next checkpoint starts building only after the current one installs, and builds from the live copy, so entity renames and merges you made carry forward.
- A checkpoint installs only once you actually reach its coverage (it used to install a hair early).

**Entity cards and marking.**

- **Upcoming entities reveal in stages.** An entity known only from the checkpoint built ahead of you now shows name and category first, one tap adds the first sentence, and another opens the full entry behind the usual spoiler confirmation. Two new settings: **Upcoming Entity Cards** (name only / first sentence right away) and **Card Shows** (first sentence only / full entry, for entities already in your installed X-Ray). Both can be overridden per book. When the tap landed on an alias, the card stays at name only even with "first sentence right away", since the sentence would give away which entry the alias belongs to.
- **The peek reads one checkpoint, never a later one**: the ahead card now uses the lowest built checkpoint that reaches your position, so an alias folded in at 100% cannot reveal itself on sight.
- Tapping a marked alias opens the card on the words you tapped, not on the entry name (which gave the link away).
- A name inside another entity's longer name now counts as the longer entity's mention everywhere: marks, mention lists, chapter appearances and counts.
- Names whose own edge is punctuation ("D.B.", "Jr.") are marked again.
- The first-sentence cut on cards handles initials, titles, CJK sentence ends and the Arabic question mark instead of stopping at the first period.
- The card no longer shows the whole entry when the first sentence ends in a non-breaking space, or when the next word starts lowercase after an ordinary word (a name like "van" or "de"); only short abbreviations such as "vs." still hold the sentence open. This is why some cards were cut and others were not.

**Other X-Ray.**

- **One more JSON repair**: a key that arrives missing its opening quote is restored, so a long build is not lost to it (the same family of fixes as v0.21.2).
- Artifact caches now record the request's token usage, shown on the artifact viewer's Info button.
- Section runs of **Counterarguments** now cache and browse like the other section artifacts.
- The X-Ray browser's root Mentions view defaults to the whole book once the book is marked Finished.
- A typeless non-fiction X-Ray is no longer read as a fiction one (it used to render every category empty).

## Book Groups and Cross-Book X-Ray (#90)

The headline of this cycle: in a group, an X-Ray lookup answers from the whole group, not just the open book, and every group now has its own page and its own settings.

- **Lookups reach the group.** Tapping a marked word, an exact dictionary or highlight match, an entity card, and the X-Ray browser's search all fall back, in order, to this book's carried list and then to the group's other X-Rays, nearest book first. Cards and rows name their source ("Carried from *Title*", "From *Title*'s X-Ray"), and a hit from another book offers **"Open in *Title*'s X-Ray"** and **"Add to this book's carried list"**.
- **The browser's search results fold the group in** as "From *Title*" groups, under the carried entries, with a plain "Nothing in the earlier books either" (or "Nothing in the other books of the group either") when there is nothing anywhere. No second tap.
- **Carried lists keep themselves up to date.** Editing a group (adding, removing, reordering, changing its kind) or writing any of its X-Rays re-seeds the members' carried lists in the background. Removing a carried entry is remembered, so it does not come back.
- **Later volumes stay closed.** In an ordered series a lookup only looks past a book once that book is read (marked **Finished**, or read to its last page) or its own spoiler protection is off. Volume 1 unread and protected keeps volumes 2 and 3 out of reach, whatever their own settings say. Passive marking, entity cards and matching selections never reach past that chain.
- **The reveal is one book at a time.** When something is held back, the results list and the no-results dialog carry a row naming the next volume ("Search *Title* too (may contain spoilers)..."), the confirmation names it too, and each confirmation opens exactly one more book. Nothing sticks: every search starts from the chain again.
- Project groups share in every direction between all members; plain groups share nothing.
- The "add this as an alias of an existing entry" offer now also appears on books that have section X-Rays (it used to fall back to a bare message there).
- **Series suggestion sees edited metadata**: a series typed into KOReader's own Book information editor now counts like one read from the file.
- Installing a checkpoint no longer drops carried entries and aliases that existed only in the live copy.
- **The group jump is spoiler-safe.** From an X-Ray entry, the "→ Group" popup lists a later volume that is still behind the spoiler chain as "(later in the series)" without checking whether the entity appears in it (knowing that a character returns is already a spoiler), and opens it only after the same confirmation the search reveal uses. From an entity page, the other book's entry opens as a read-only view over the page instead of switching X-Rays. Entity cards and pages also say where else in the group the entity appears ("Also in *Title*'s X-Ray"), never naming a later volume the spoiler chain still holds back.

**Group Hub and group settings.**

- **Every group has a page.** Main menu > Groups opens the Groups list: one row per group with its kind icon and "Kind · N books"; tap for the group's hub, hold to move, rename, change the kind or delete it, and the title-bar menu creates groups (blank, from a folder, from a collection, or with the open book) and sorts the list by name or by kind (a one-shot sort; you can still move groups by hand). The list itself also offers "New group from series ..." when the open book carries a series tag.
- **The Group Hub** shows a group's action rows first (Group Settings, the X-Ray fold row, and a Series/Project/Group Chat/Action row that opens the library dialog with the members pre-selected), then the members in order (tap for a book's Book Hub, hold to move, open or remove it), then the add rows. Its title-bar menu carries the add flows, Kind, Rename and Delete; the up-arrow returns to the list. The Book Hub's Group row, the artifact viewers' "→ Group" button and the Quick Actions "Group Hub" utility all land on the book's hub (a chooser when it is in several groups); the X-Ray browser's own "→ Group" keeps opening the members popup, which has a "Group hub..." row. A Book Hub opened from a group gets an up-arrow back to it.
- **Group settings.** A group can set the same settings a book can: domain, research mode, Background, spoiler protection, automatic X-Ray, new X-Ray categories and depth, and the three languages, through the same pickers ("For this group"). Setting a value offers to apply it to every member; members then follow the group ("Follow group X (value)" on their Book Settings rows and in every picker) until they pick their own value, which the Group Settings screen lists as "not following" with "Re-apply to all". Books added to a group that sets values are asked once; leaving or deleting a group returns its books to the global settings, and a book whose group no longer exists (a groups file restored from an older backup, say) simply follows the global settings again.
- **Collections as a source.** The book picker browses KOReader collections beside history and folders; groups can be created from a collection or filled with one, and the series scan can look in a collection.
- A closed book's chat opened beside another open book (from a group hub, for instance) gets its own dialog again instead of the open book's actions and title.
- Crossing the next built checkpoint installs it at any spacing; a spacing above 25% used to refuse the install (for good with automatic X-Ray off).

## Chat Viewer

- **Math renders as readable formulas** (#105). LaTeX in a response is shown with Greek letters, real operators, superscripts and subscripts, accents, roots, and fractions as `a/b`, with display formulas centered. Markdown view only, and display only: saved chats, copies and exports keep the original notation, which Obsidian and similar apps render fully. Toggle in **Settings > Display Settings > Rendering > Render Math Formulas** (on by default).
- **New Window Size setting** (Standard / Expanded) in **Settings > Display Settings > Window Size** for chat, artifact, translate, dictionary and quiz windows, also on each window's gear menu. Expanded leaves only a hairline around the window; compact dictionary popups are unaffected.
- Indented continuation lines under a list item render as part of that item instead of an empty bullet.
- A response whose markdown is cut short mid-code-fence renders instead of falling back to plain text, and emphasis characters inside math no longer scramble the rest of the answer.
- **Exports no longer fail on Kindle** ("Invalid argument"): filenames built from a title are cut on a character boundary.
- **Hold Close to get back to the page.** A long press on the Close button closes the chat window, any dictionary windows under it and the highlight menu in one gesture, instead of tapping through them one at a time.
- A reply that arrives while you have scrolled back to reread lands where you were reading, not on the last question marker (from the second reply on, the marker used to win).
- Pressing Stop or closing the window in the moment after a streamed answer has finished, while the plugin is still reading the provider's trailing rate-limit information, no longer reports the complete answer as cancelled.

## Providers and Models

- **NVIDIA is a new built-in provider**: free developer program, email only, no card and no identity check. Curated model list from a live catalog probe, reasoning profile, book tools on the models where forced tool use actually worked, no web search. Models retired by the host on 2026-08-26 are pruned, response parsing (including reasoning content) is fixed, and speed tiers are placed from measured latency.
- **Test provider** now shows the server's own error detail when a reachability check fails, instead of a bare failure.
- **OpenCode Zen and OpenCode Go are two new providers on one account** (#107): Zen is the pay-as-you-go catalog of open-weight models, Go the subscription with its own model list. Zen's built-in list grew by nine models (GLM 5, 5.1 and 5.2, MiniMax M2.5, Kimi K2.5, Qwen 3.5 Plus and 3.6 Plus, and two experimental ids), each with its own reasoning and output profile. Each has its own key entry (the same key string under `opencode` and `opencode_go`), both send the conversation header OpenCode requires, and reasoning effort is one setting for both. GPT, Claude and Gemini through OpenCode are not supported yet (they use other endpoints).
- **One conversation id per chat.** The id a chat is saved under is the id the wire saw, and it rides to the hosts that use one (OpenCode's session header, OpenRouter's session id, OpenAI's prompt cache key). No other host receives it.
- **Gemini's content filter is relaxed for books by default.** Google's own filter blocks answers about violent or sexual passages, and the reply used to arrive empty and unexplained. The plugin now turns the four adjustable filter categories off for its own requests. **Settings > Advanced > Provider Settings > Gemini Content Filter** ("Relaxed for books" by default, "Google default" restores Google's), also on the Gemini model menu.
- **When a provider cuts a response short, it says so.** A finish reason outside the normal set (a safety or content filter, a recitation block, a refusal) used to surface as "Unexpected response format" when nothing came back, or as a silently shortened answer. The reason is now named: as the error when there is no text, and as a line under a partial answer, which also keeps that answer from being cached as if it were complete. Streamed replies included.
- **Groq is now a tested provider.** A reader's free key (the #106 report) let the maintainer's model audit run against Groq itself: the live model list, and the full capability battery on every built-in Groq model. The gpt-oss models reason by default with low, medium or high effort, answer up to 65,536 tokens and take the book tools; the compound models take no reasoning setting and no tools, and answer up to 8,192 tokens. Everything the plugin had assumed from Groq's documentation held, so Groq loses its community marker in the provider list.

**Requests that fit your plan (#106).**

Some providers count the answer budget a request *asks for* against a per-minute token allowance, before running anything. Since v0.21.0 the plugin asks for a large budget by default, so on Groq's free plan (8,000 tokens a minute) every request was refused, including one-word dictionary lookups, and the error text blamed book size.

- The plugin now learns your plan's per-minute allowance from the provider's own rate-limit headers (Groq, Cerebras, OpenAI) and sizes the answer budget to fit it before sending. It learns on the first real answer, streamed ones included, and from "Test provider".
- If a request is refused all the same, a refusal that names its numbers teaches the plan's allowance: one whose answer budget was the problem is sent once more at a budget those numbers allow, and every later request in that session is sized to fit the allowance. A burst refusal (your minute's allowance is already spent) is not resent, because it refills with time.
- **One honest tip per refusal.** A burst refusal ("you used your minute") says to wait; an admission refusal explains what actually happened, and when the request itself is bigger than the allowance it names the lever for the surface you are on (scope and a new chat in a book chat, folders in the library, the artifact itself in artifact chat). A small one-word lookup refused this way no longer gets the old "lower Max Text Characters" advice, which could not have helped.
- If the prompt alone cannot fit your plan or the model's context window, a notice says so before sending, and the request is sent anyway rather than blocked locally.
- A background X-Ray build stopped this way now reports "request too large" instead of "unusable response", and does not retry on a 60-second timer for something deterministic. A per-minute refusal that states no numbers (Anthropic, Gemini, Cerebras) or one the bucket will admit once it refills counts as a burst: the wait tip, and the build retries once after a minute.
- A pinned answer budget cut to fit the plan tells you it was cut.
- The self-heal also recognizes OpenRouter's context-window wording, pre-caps the next request from it, and explains the window instead of blaming book text.
- **The provider's own wait, as a number.** When a refusal names how long to wait (Groq's and OpenAI's "try again in 5s", Gemini's retry delay, or the retry-after header Anthropic and OpenRouter send), the wait tip says "about N seconds" instead of "wait", and a background X-Ray build waits exactly that long before its one retry instead of a fixed minute (a wait past ten minutes stops the build instead, with the resume rows).
- **Account walls are named as such.** Used-up credits, an empty balance or a spending cap (OpenAI's insufficient_quota, Anthropic's "credit balance is too low" and monthly spend cap, DeepSeek's "Insufficient Balance", OpenRouter's "insufficient credits") get a tip that points at the account instead of "wait and try again", the error stays on screen with a Try again button for after you top up, and a background X-Ray build stops with "account credits or billing" instead of retrying. OpenRouter's "can only afford N tokens" refusal (its credit check counts the whole answer budget, so a low-credit key failed a one-line question) is resent once with that answer budget when N is worth an answer.
- Error messages now carry the provider's own error code in parentheses, such as "(insufficient_quota)" or "(rate_limit_exceeded)", which is what tells two providers' identical sentences apart.
- Checked on a real free Groq key (2026-09-07): the plugin learned the 8,000-token allowance from Groq's headers on the first answer and sized the next request to fit. Groq has since changed its limiter: the gpt-oss models now admit the old 32,768 budget (the photographed refusal did not reproduce), while some models carry a separate output-tokens-per-minute bucket (1,000 a minute on the preview Qwen models of that account). Both of Groq's new wordings are in the plugin's corpus: one that can never fit is resent once with a budget under the output limit, a spent bucket gets the wait tip with Groq's own seconds.

**Ollama**

- The plugin asks the server how big the loaded model's context window actually is before sending a prompt that will not fit, warns with the real number, and says afterwards when only part of the request reached the model (Ollama silently cuts the earliest book text to fit its window). New "Context window" row in the Ollama model menu.

**API keys**

- Keys are cleaned to printable characters when read, which heals a key pasted with an invisible character or an interior line break (the Kindle case where a key copied out of a wrapped text file kept returning 401). Saving a key reports how many stray characters were removed.

## Storage

**Per-book plugin data left KOReader's metadata.lua** (#72).

- Chats now live in `<book>.sdr/koassistant_chats.lua`, and every per-book plugin setting in `<book>.sdr/koassistant_book_settings.lua`, next to the cache and notebook files the plugin already kept there.
- **The move is automatic**: a bulk pass runs once at start-up, with catch-up passes when a book is opened or first touched, and it copies and verifies before removing anything.
- Consequences: KOReader's **"Reset this document"** no longer wipes your chats and per-book settings, and KOReader's optional metadata archive no longer carries chats.
- A book store now follows a mid-session change of KOReader's "Book metadata location" instead of leaving its file behind.

**Backup and restore**

- **Book groups are included in backups** (and per-book settings ride along as well).
- **Restoring a backup made before the chat storage change now imports its chats** instead of restoring them where nothing reads them.
- "Quick: Fresh start" also clears the leftover chat-import backup folder once migration is complete.
- Deleting a notebook now also clears the book's pointer to it, so the book no longer refers to a notebook that is gone.

## Other

- **Console Debug is scoped to the plugin**: turning it on brings back the plugin's own tracing without raising KOReader's global log level (which used to bury it under core's per-paint output). Routine tracing is no longer written to `crash.log` when debug is off, and plugin tracing is also emitted when KOReader's own verbose logging is on. A few per-page-turn lines that Console Debug used to write at the info level moved to the debug level too, and the marking line no longer lists entity names.
- **One long-press menu on every action button.** Holding an action in the highlight menu, the dictionary popup, Quick Actions, an input dialog or the file browser menu now opens the same small menu instead of a description on some surfaces and nothing on others: the description at the top, "Add to" or "Remove from" this menu, "Other placements..." for the rest of its menus, and "Edit...", "Duplicate as custom action..." or "Reset to default". Adding or removing takes effect where you are standing, without a trip to Settings.
- **New `{user_input}` placeholder for custom actions.** Text typed in the input dialog can be placed inside a prompt where you want it, instead of only being appended at the end. It is in the editor's placeholder list as "Typed Input"; before this the placeholder was offered but never filled in, so the braces were sent to the model as they were.
- **The update check reads version tags correctly.** Two-part tags (v0.22) are no longer skipped when looking for the newest release, and pre-release tags sort the way they should: rc.11 is newer than rc.9, alpha comes before beta before rc, and a final release beats its own release candidate.
- The Domain & Research picker opens on the book tab whenever a book is open, from the input dialog's Domain chip and from holding the Quick Settings Domain tile; it used to open on Global until the book had an override of its own.
- Settings rows that open a picker or a manager (Categories and Depth of New X-Rays, the action and domain managers, the menu ordering managers, backups, the index tools, Test Connection, Check for Updates, About) now leave the settings menu open behind them instead of closing the whole menu.
- Section-scoped artifacts are back on the Book Hub (only the X-Ray versions group is filtered out there, since the X-Ray browser owns it).
- **Highlight menu defaults reordered** so the two conditional rows sit last: Translate, Explain, Quick Explain, Summarize, Quick Define, Dictionary, then Look up in X-Ray and Generate Image. Existing users keep their configured list.
- **Edited book metadata is honored everywhere**: a title or author changed in KOReader's Book information now shows and is sent in artifact and notebook pickers, groups, merge labels, the library scan, notebook filenames, backup labels and the chat history browser. The chat history index carries it and refreshes the moment you edit it.
- The chat history browser opens without reading each book's sidecar, which is noticeably faster on a large library.
- The per-book Quick Answer default now resolves the book the action targets, not whichever book is open.
- Quiz generation asks for answer options of comparable length, specificity and style.
- Text extraction reaches the document's last page (whole-document builds used to stop at the start of it), SSE `id:` and `retry:` lines from a streaming server are ignored instead of read as data, nested list bullets are drawn as filled dots at every depth instead of hollow circles and squares, and long code lines wrap in the chat viewer instead of being cut off at the right edge.

## Work in Progress

- **Cross-book lookups, the Group Hub and group settings** are new and touch a lot of surfaces. Device reports welcome; the group settings for chat behavior (tools, web search, effort dials, contexts) are planned for the next version.
- **Request sizing** is verified against a local stub and, for the header path, on a real free Groq key. A live Groq refusal has not been reproduced (Groq admitted the old budget on 2026-09-07), so the refusal path stands on Groq's own wording from the report.
- **AI Book Tools** stays off by default while retrieval quality matures.
- **Setup Wizard v2** is still built but not switched on.

## How You Can Help

- **Device reports**, especially on the X-Ray first-build confirmations, cross-book lookups in a series, and the storage move.
- **Translations**: review passes on [Weblate](https://hosted.weblate.org/engage/koassistant/).
- **Bug reports and feature requests.**
