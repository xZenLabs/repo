# v1.22 · 2026-11-23

## v1.22

### Auto-annotated translation (Readlang-style)

- New "Translate as Annotation" switch (Other Settings): when the built-in
  KOReader Translate action is replaced by the Assistant, its answer is
  saved as the note of a fresh highlight and shown in a small floating
  overlay just above the selection (below it when there is no room above,
  centered when neither side fits), with the save status as the title line.
  Tap or Back dismisses it, and it closes itself after a few seconds.
- The Assistant's own Translate buttons keep the result window; any failure
  falls back to it, so nothing is lost. Built-in translation keeps the
  source formatting and offline availability; the plugin version gives the
  full AI answer in the configured response language.

### Flashcards and AnkiDroid

- New flashcard feature: build editable cards from a look-up, with AnkiDroid
  TSV export, so vocabulary moves into AnkiDroid in one step.
- Viewer closes after a successful Annotate; manual and automatic paths
  share one save function.

### Dictionary

- AI Dictionary output gains a pronunciation section.

### OTA / updates

- Updates download straight from codeload.github.com, and the OTA input
  accepts user/repo[@ref] so updates can come from a fork or a specific ref.
- Hardened flashcards preview fallback, trimmed reuse and menu truncation.
- ARMv7 softfp builds stay compatible with ARMv6 (Kindle K3); CPU
  instruction-set mismatches no longer crash.

### Fixes

- JSON schema auto-downgrade forgives reordered percent signs in translation
  placeholders.
- Translating a look-up no longer leaves the viewer open.

# v1.21 · 2026-10-22

## v1.21

This release adds Book Identify, recommended for TXT books that carry no
metadata by default.

### Book Identify

- New Identify (AI) button in the file manager long-press row, plus an
  Identify This Book reader action: title and author are inferred from the
  opening text, optionally verified with web search, and written to custom
  metadata so Book Information shows them.
- Books without metadata no longer get fabricated placeholders: answers
  follow the response language, and queries ground on percent progress with
  auto-attached surrounding text.

### Result viewer

- The streaming dialog shows Provider/Model as the title subtitle.

### Fixes

- Recap stays quiet for barely-started books: below 3% progress auto recap
  skips its prompt and the file manager entry suggests starting to read
  first.
- File manager AI buttons follow the active provider and web-search tool.
- Opening-text extraction no longer collapses to one character on short
  books.
- For unreadable formats, Identify sends the reader to the book instead of
  failing.

# v1.20 · 2026-10-13

## AI Assistant v1.20 - Bug fix release

### Fixes

- **Waiting animation kept running after a cancelled or failed request.** Closing the stream dialog before the first response text arrived, or any request that ended with an error, empty response, tool-only response, or exception before text, left the waiting animation scheduled. On Kobo devices this blocked suspend and drained the battery. The animation is now cancelled on close and on every exit path. Thanks to @fernandeslouro for the report and the patch in #215.
- **Slovak translation corrections.** Several Slovak strings were corrected after an audit.

### Upgrade notes

- If you are updating from v1.18 or earlier and an OTA download failed with an error such as `attempt to compare number with string`, the cause was an interrupted network transfer, just try again until the download finished. This is fixed from v1.19 onward. Use the current release to update.

# v1.19 · 2026-10-09

## v1.19

This release centers on the result viewer: text layout controls, custom
fonts, file manager integration, and a reorganized settings menu.

### Result viewer

- The result viewer is now a chat transcript: user turns and answers share
  one scrollable conversation. Bubbles size by turn length: one-liners keep
  a compact shape, long selections take the full page, and caption-only
  action labels hug the right edge instead of reading as a wide empty box.
- Recursive queries: select text in any answer and run another prompt on it;
  viewers stack so each follow-up keeps its own context. The acted-on
  selection can move out of the caption into its own muted band above the
  question (Response Settings > Show Highlighted Text), so the original is
  easy to compare with the follow-up answer.
- Turns show book identity (title/author) in the bubble; minimalist mode
  keeps only the answer actions for a quieter layout.
- Streaming dialog shows a reasoning/answer status row, and the reasoning
  switch now applies to turns already on screen.
- Mixed-direction replies render per block (code stays LTR), and a Response
  Font picker lists installed KOReader fonts and registers the choice with
  MuPDF.

### Settings menu

- Response Settings is reorganized around display: a Text Appearance submenu
  groups Text Size, Text Direction (Auto/RTL/LTR), and Response Font; the
  old RTL checkbox in the language dialog is gone.
- New Minimalist Mode master switch shows the answer alone and takes over
  Reasoning Text and Follow-up Questions while active.
- New Show Highlighted Text switch gives the acted-on selection its own
  block above the question.
- Dictionary settings gain Auto Add Word to Vocabulary Builder.

### File browser

- Book Info (AI) and Recap (AI) run directly from the file manager
  long-press menu on unopened books (FileManager, History, Collections,
  File Searcher), no need to open the book first.

### Dictionary and Vocabulary Builder

- Dictionary lookups can auto-add to the Vocabulary Builder; the builder
  button is always offered and a failed auto-add is reported on both paths.

### Safety

- An unrecognized web-search key now fails closed instead of silently
  enabling search; each search tool stores only the credential it declares.

### Fixes

- Default prompts include KOReader context.
- Web search is preserved on feature follow-ups.
- Recap reads last-read time from history (with sidecar mtime fallback)
  instead of unreliable file atime.
- Model picker no longer shows a false selection after paging; the staged
  pick survives page changes.
- API connection tests use a larger token budget so reasoning models return
  a usable answer.
- Text direction label refreshes without closing the options menu.
- Search keyword line is flush left.

### l10n

- The localization pipeline no longer ships wrong-language or misplaced
  strings (some locales carried text in the wrong language); wordless
  markup-only templates are out of the msgids. Catalogues refreshed in this
  cycle.

# v1.18 · 2026-09-23

#### Highlights
More places inside KOReader where AI is one tap away:
- File Manager long-press: Book Info (AI) and Recap (AI)
- Book Description Translate
- Smarter AI Dictionary with configurable output
- Notebook and result viewers with a consistent reading experience

#### What's New

**More KOReader Entry Points**
- **File Manager long-press** — run Book Info (AI) and Recap (AI) without opening the book.
- **Book Description Translate** — translate the book blurb directly from the description popup.
- **Smarter Translate routing** — short selections ask once (Translate / Dictionary / Cancel) and remember your choice; long selections always translate.

**AI Dictionary, Less Clutter**
- Output sections are now configurable with Concise / Standard / Full presets, defaulting to a shorter Standard set. Concise mode additionally favors brevity over book-awareness.

**Result Viewer and Notebook Viewer**
- **Result viewer (ChatGPTViewer)** — two-row buttons with paging Find, plus Vocabulary Builder and Annotate actions.
- **Notebook viewer** — notebooks open in a TextViewer-based Markdown viewer with table support.
- Both viewers now share the same CSS, so AI answers and saved notes read the same.

**AI Notes (formerly General Notebooks)**
- Renamed to **AI Notes** to distinguish them from KOReader's built-in reading notes.
- By default a single conversation log (`ai_notes.md`): AI answers and quick notes are appended to it, with optional auto-save per conversation.
- **Multiple AI Notes** — enable it in AI Notes Settings to create several notes and choose which one is active.
- Book notes save to per-book files (`<AI Notes folder>/<book>.md`) inside your AI Notes folder, which is configurable in Settings and auto-created on write.

**Provider & Model Polish**
- Model picker and provider forms are testable in place, with explicit confirmation and clearer failure reports.
- API errors surface the provider's own message with HTTP status; connection-test output no longer leaks request bodies.

#### Improvements & Fixes
- Highlight menu: stale menus close after add/remove, selection stays alive for Annotate.
- Anthropic models support built-in web search.
- Reasoning (model thinking) renders dimmed above the answer and only when enabled.
- Streaming title shows the request origin; provider/model identity is frozen per request.
- Dictionary popup entries moved into Dictionary Settings; KOReader Tweaks renamed to Other Settings.

#### Translations
All languages refreshed with the new dictionary, viewer, and notebook strings.
