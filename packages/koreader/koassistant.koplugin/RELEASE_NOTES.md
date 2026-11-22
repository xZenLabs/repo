# v0.25.0 · 2026-11-21

# KOAssistant v0.25.0 Release Notes

Answers are easier to read while they arrive, you get more control over the names an X-Ray underlines in your book, pictures get one popup for all their settings, and there are new models and a new provider, Amazon Bedrock. A long list of bugs is fixed, among them a rare crash and a freeze when the screen turned with the chat input open.

## Highlights

- **Answers arrive formatted.** Bold, headings and lists (Markdown) show as the text comes in, and the window stays on the first page so you can start reading at the top.
- **The minimal popup shows formatted text too**, and can sit at the bottom of the screen like a footnote.
- **Proper fonts for Arabic, Persian, Urdu, Hindi (and other Devanagari languages) and emoji**, with nothing to install. Right-to-left text reads in the right direction.
- **You decide which names an X-Ray underlines.** A new screen, Names and matching…, can stop a name from being underlined, or underline it only when it is written with a capital.
- **X-Rays tell you more**: a Conclusion at the end of the book, where a name first appears and where you last saw it, and a new short preset, Who's who.
- **Pictures have one popup** for a note to guide the picture, the X-Ray entries to draw from and every picture setting.
- **New models** from Anthropic, OpenAI, Google and others, **and a new provider**, Amazon Bedrock.
- **Deleting a book keeps its notebook**, and backup and restore take better care of what you made.

## Changes

- **Answers no longer scroll by themselves.** A new answer stays on its first page while the rest arrives, and you turn the pages. To have it follow the text again: Settings → Chat & Export Settings → Streaming → Auto-scroll Streaming, or tap Autoscroll in the window for one answer. An X-Ray being built is still followed.
- **Formatting shows while the answer arrives.** Markdown While Streaming, in the same menu, turns it off.
- **When a chat opens on its newest reply, the reply starts on a page of its own.** Your question is on the page before it.
- **Three right-to-left switches are gone** (Auto RTL mode for Chat, Text Mode for RTL Dictionary, Text Mode for RTL Translate). Right-to-left text now displays properly in the normal view: each paragraph, list and table in its own direction, also where Arabic is mixed with English. A dictionary window for a right-to-left language now opens formatted, where it used to open in plain text. If you prefer plain text, Text Mode for Dictionary and the MD ON / TXT ON button are still there.
- **AI merge between books is experimental for now.** It is a paid step that combines the X-Rays of two books, and it can attach a name to the wrong entry; how often has not been measured yet. The app no longer offers it by itself and the Group Hub has no row for it, but you can still start one from an X-Ray's Link and merge… menu. What the earlier books of a series know is still carried into the later ones automatically, for free.
- **Some default models changed.** If you never picked a model yourself, you move to your provider's new default, and a notice tells you once: OpenAI now defaults to GPT-6.1 Terra, Mistral to Mistral Large 4, Kimi to Kimi K3 and Qwen to Qwen4-Max, among others. A model you picked yourself stays, unless its provider retired it: then it moves to the replacement, also with a notice.
- **Pictures: your chat model now writes the picture's description (its prompt).** It follows the book more closely than the fast model did, and it is slower and costs more. To go back: Settings → Advanced → Image Generation → Prompt writer.
- **Quick Explain uses your domain and the book's Background note**, as Explain does. To switch that off, hold Quick Explain, tap Edit… and set its Domain to None.
- **Deleting a book keeps its notebook.** It moves to the KOAssistant notebooks folder, a message says where, and Browse Notebooks lists it. The book's chats and saved results are still deleted with the book, and a whole folder deleted in KOReader still takes the notebooks inside it along.
- **The X-Ray action's long-press menu no longer offers Without book info.** It did not fully work: an X-Ray built in checkpoints still sent the book's title. To build an X-Ray that never names the book, set Book info to None for that book (Book Settings → Privacy & Data).

## New and Improved

### Chat windows

- Dots move after the window's title until the answer is complete, and the window no longer jumps when the answer finishes.
- Numbered lists keep their numbers (no more 1, 1, 1), and checklists show boxes (☐ ☑).
- A message you typed on several lines is shown that way, and a highlight of several paragraphs keeps its paragraphs.
- Your place in a chat is kept when you turn the device, resize the window or switch between Markdown and Plain Text, and the reply box, Save Chat and New Tag stay on top with what you typed. On Kobo and Kindle models with a rotation sensor, the chat window now turns with the device.
- Minimal popup: set to Always, it scrolls a long answer. Hold a word in it to look the word up, or select more text for the usual menu. The new Popup Style setting (Settings → Minimal Popup) chooses between a floating box and a panel at the bottom of the screen.
- A new setting picks the font for Arabic-script text: Settings → Display Settings → Rendering → Right-to-left text font.

### X-Ray

- A new screen for an entry's names, **Names and matching…** (in the entry's More… menu). Any name can be switched off, so a name that is also an everyday phrase stops marking ordinary sentences, or set to capitals only, so a character called Will is not underlined in every "will". KOAssistant also decides the capitals question by itself from how the book writes each name, and the screen shows what it counted.
- An X-Ray that reaches the end of the book ends with a **Conclusion** instead of Current State. An X-Ray that is already at 100% gets one when it is rebuilt.
- The creation form explains each way of building under the option you pick: what you get and what it costs. A line under the checkpoint options says what spoiler protection will show you (tap it to change the setting), and another warns when a fast model is a poor fit for your choice. The form now fits on an e-reader's screen without scrolling.
- A new preset, **Who's who**: just the cast, one line each. The shortest and cheapest X-Ray.
- An X-Ray's last section is called **Current State** in every setting (some screens said "status block"), the Categories button lists what is ticked instead of a preset's name, and Info (in the X-Ray's ☰ menu) shows what an X-Ray was built with.
- Names with an apostrophe or a hyphen (King's Landing, Mary-Jane) are found in books that print curly apostrophes and typographic hyphens.
- A change to an X-Ray shows in the page's underlines right away, with no page turn.
- When you read along, a new character who shares a name with one already in the X-Ray gets an entry of their own instead of taking over the other one's.
- An entry's page shows **First appears** and **Last seen** with chapter and page (EPUB). With spoiler protection on, Last seen stops where you have read.
- When a word on your page is underlined because it matches someone who appears only later in the book, the card lets you switch that underline off without telling you who it is.

### Series and groups

- Carried entries stay in step with your groups. If you take a book out of a group, delete a group, change its kind or reorder a series, each X-Ray lets go of what it carried from books it no longer takes entries from. Entries you carried or added by hand stay, and so does what an AI merge added.
- In a series, the Group Hub asks before it opens a later volume than the one you came from.

### Dictionary and translation

- KOReader's own dictionary can be reached while the dictionary bypass is on: use the Dictionary row in the highlight menu (a very long press on a word opens that menu). It also opens for a word that is an X-Ray name, as does Dictionary in KOAssistant's own selection popup.
- Translate Page shows the page's paragraphs apart instead of as one block. (A PDF page keeps its lines joined, as before.)

### Pictures

- Generate Image, Illustrate… and a gallery picture's Image settings… all open the same popup: a note to guide the picture, the X-Ray entries to draw from, then Prompt, Style, Shape, Detail, Provider and Model.
- A note that names a character or a place brings in that X-Ray entry, so a passage that only says "she" can still be drawn right.
- A picture remembers which X-Ray entries it shows, and an entry's More… menu has Pictures (N)… to see them.
- Pictures invent less: when the text does not say where a moment happens, the background stays simple.
- A picture appears sooner on a slow e-reader once the provider has answered.

### Models and providers

- New models: Claude Fable 5.2; GPT-6.2 Sol and Astra, and GPT-6.1 Terra; Gemini 4 Carbon and Hydrogen; Qwen4-Max; Kimi K3 and K3.1 Pro; Mistral Large 4; and the picture models gpt-image-2.6-flare (OpenAI's default) and gpt-image-2.6-sunburst. OpenRouter and similar services list the same models.
- **Amazon Bedrock** is a new provider, contributed by a user (#113): enter a Bedrock API key and pick your region under Settings → Advanced → Provider Settings. For now its answers appear all at once instead of word by word, and the reasoning settings have no effect on it.
- API keys (#125): the key window reminds you to check the start of a key you copied inside KOReader, where a selection can miss the first characters. An "API key not valid" error now shows which key was sent: its name, its first 3 characters and its length.
- X-Rays, summaries and other saved results built with Claude cost less: about 18% for an X-Ray of a whole book on Claude Sonnet 5.5.

### Actions and settings

- An action run on one section of a book (a summary, a quiz, the Reading Guide and others) now tells the model that it is looking at that section, not at the whole book. Small models used to reply that they could not summarize a whole book from one chapter.
- Built-in actions that leave your domain out (Translate, Fact Check and others; the wiki lists them) can now be set to use it: choose Global for Domain in the action's settings.
- The highlight menu shows up to 30 KOAssistant actions (15 before).

## Fixed

### Crashes and freezes

- A rare crash that closed KOReader a few seconds after work in the background finished: the indexing of names after an X-Ray is built or its book opened, Fetch models, Test provider, an update check, a book search, a picture request.
- A freeze when the screen turned, or the window was resized, while the chat input was open.
- On Android e-readers that go to sleep a few seconds after the last touch (a Boox, for one), a lookup, a download or a book search stopped until you touched the screen. Waiting screens now keep moving, which keeps the device awake (#126).
- Fetch models and Test provider froze the app while they ran. They now show their progress, and a tap stops them (#126).
- KOReader could crash on text with a broken character (a held word, a lookup), and when Generate Image was tapped on a highlight that crossed an indented paragraph.
- KOReader started slowly every time for people who have used the plugin since before v0.22.0, when one book's data could not be moved during that update.
- KOReader froze for seconds on a book with thousands of X-Ray entries (a long series).
- The Reading position, Library and Reading habits rows of Book Settings → Privacy & Data crashed on their For this book tab, and the quiz window could crash on Show Answer.

### Chat windows

- Two formatted words in a row (bold then italic, two links) lost the space between them, since v0.24.0.
- An answer with a command or code under a numbered step could show as unformatted text.
- A word in a narrow table column could be split over two lines.
- Emoji sent by some local or self-hosted AI servers came out as broken characters, in the window and in the saved chat.
- The Plain Text view opened a few lines above the newest reply.
- The last words of an answer could be missing with some providers.
- A request to answer in another language ("answer in Arabic") was often ignored.

### X-Ray

- After a Library, Series or Group chat had been opened, X-Rays were shown but not saved and checkpoint builds stopped, until KOReader was restarted (#123).
- The Preset, Categories, Depth, Type and Carried Entries rows under Settings → Reading & Library → X-Ray did nothing in v0.24.0 and v0.24.1 (#123).
- With spoiler protection on, an X-Ray built in checkpoints could, in rare cases, show a version that reached past where you had read.
- A chat or an AI Wiki article about an X-Ray entry of another book than the open one used the open book's spoiler setting, domain and languages.
- With Card Shows: Full entry, the X-Ray card showed only the description. It now shows the entry's full text.
- A short name was counted inside longer words: in Vietnamese, Hindi and other Indic scripts, polytonic Greek and Georgian, and in PDFs ("Ann" in "Hannah").
- Look up in X-Ray could ignore a name's Not matched or Capitals only choice, and missed names typed in another case in Cyrillic, Greek and accented Latin letters.
- Mentions and Chapter Appearances could wait for ever after the underlines had been turned off.
- A chat started from an X-Ray entry with one of the action buttons was missing from the X-Ray chats row.
- After an X-Ray was updated or rebuilt, AI merging the series ran, and charged for, merges that were already done.
- A long checkpoint build pauses again for your review before an unusually large step; that safeguard had stopped working.
- The confirmation before an X-Ray is rebuilt in checkpoints promised that the old version would be archived even when version archiving was off.
- After Delete All, a book's automatic X-Ray could start again by itself.
- In a group with thirteen or more X-Rayed books, every page turn was slow.

### Privacy and spoilers

- With Book info on None, sending your notebook revealed the book's title: the title line at the top of the notebook went along. It is no longer sent.
- With Book info on Title only, some actions still sent the author's name.
- Page bookmarks were sent along with your highlights.
- A saved result made from your notes was treated as holding highlights only. It now asks before your notes are shared again, when you chat about it, attach it or update it; pinned answers ask the same way.
- An X-Ray that was built with your highlights could not be continued when Highlights was set to Ask.
- AI Wiki from a highlight or the dictionary popup silently left out the text around the selection instead of asking.
- After you cancelled the question about sharing your data, the options you had picked for that cancelled action (another model, a part of the book) could still apply to your next request.
- If you had switched the Spoiler chip off in a chat, an action started afterwards from the file browser, or from Quick Actions right after a library chat, could run without spoiler protection. A later part of the book that you confirmed for one message also switched the spoiler reminder off for the first message of your next chat.
- In Chinese, Japanese, Hindi and Arabic text, "the sentence around your selection" was the whole paragraph.
- The Reading position setting now says when your position is sent. The setting itself did not change.

### Chats and attachments

- Every reply in a chat also sent your first question a second time, so chats cost more than they should.
- Some answers could damage your saved chats so that they would not open. They open again.
- Add to Notebook could write into the wrong book's notebook: in a saved Summary or Recap opened after you had continued another book's chat from Chat History.
- After a chat about another book from the file browser, the dictionary popup's Look up in X-Ray and Generate Image buttons, the dictionary bypass and the X-Ray card could act on that book instead of the open one.
- A chat about a saved result that you started with another model ran on your main model once the question about your data had been answered.
- Library chats could not be tagged.
- Text with a word in curly brackets, such as "{title}", in a selection, a typed message or the book's text had that word replaced before it was sent.
- A scanned PDF with no text was sent as empty pages. An action now says that no text could be extracted.
- Attachments waiting in the chat box when you ran an action that takes none were sent later with your first reply. They are now dropped, and a message says so. A text file that is not UTF-8 is refused instead of being sent as unreadable characters.

### Providers and answers

- An answer cut off at the provider's length limit could be saved as if it were complete (an X-Ray, a summary). It is now recognized as cut on every provider.
- On e-readers and Android, an error that arrived in the middle of an answer lost the provider's own reason: an account that was out of credit was told it had sent too many requests.
- A reasoning level that your model does not offer made the request fail. The model's default level is used instead.
- A key you add in the API key window is used right away. Before, a second key waited until you tapped it in the key list, so replacing a dead key kept sending the old one (#125).
- Test provider called correct answers from OpenAI and DeepSeek unreadable.
- Saving a first API key switched the provider if you used the OpenAI Subscription, Ollama or a key in configuration.lua.
- Answers from some self-hosted AI servers were marked as stopped early, so X-Rays and other results were not saved.

### Actions and menus

- Saving one of your own actions keeps everything you did not change. Before, every Save dropped the action's domain, temperature and several other settings. A built-in action saved with nothing changed stays a built-in and keeps following updates.
- A custom_actions.lua file with an error removed its actions from every menu for good. Their places are now kept, and a notice names the error and its line.
- Deleting one of your actions removes its gestures and clears a dictionary bypass that pointed at it. Settings → Gestures lists a gesture whose action is gone, so you can remove it.
- The X-Ray popup and the other result popups end with Close instead of Cancel: closing them cancels nothing, and a build that is running goes on.
- Cancelling a section list, the reasoning model list or the Quick Answer preset's model lists returns you to the popup you came from instead of leaving you on the page.
- A new domain or behavior could silently take the place of one you had deleted, in the books and actions that used the deleted one.

### Backups, notebooks and updates

- A backup that could not be written completely (a nearly full card) reported success. It now fails and says why.
- A restore in Merge mode replaced what you had made after the backup. It now keeps your newer groups, your general and library pinned answers and your own domains, behaviors and providers.
- A restore that failed halfway could report success, or say "rolled back" while newer chats or groups were gone.
- After a restore, the next settings change could write the old settings back, and groups or the menu places of your actions could be overwritten.
- Changing where notebooks are saved could lose a notebook when the copy failed (a full card).
- A failed automatic update check was tried again every time you opened or closed a book. Attempts are now at least 30 minutes apart (#121).

And many smaller fixes.

## How You Can Help

- **Bug reports, device reports and feature requests**: [open an issue](https://github.com/zeeyado/koassistant.koplugin/issues) and say which device you use.
- **Translations**: review passes on [Weblate](https://hosted.weblate.org/engage/koassistant/).

Every feature is described in the [wiki](https://github.com/zeeyado/koassistant.koplugin/wiki).

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
