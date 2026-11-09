# 26.11.9 · 2026-11-09

## Entity Underlining (optional new feature)

You can now have X-Ray underline characters, locations, historical figures, and terms directly on your book pages as you read. Tapping any underlined name brings up an instant description pop-up without losing your place.

A huge thank you to @Dukko for creating the original user patch that inspired and kicked off this native feature!

**This feature is opt-in and fully configurable.**

### What's New

- **In-Book Entity Underlining**: Automatically underlines people, places, and terms found in your X-Ray data. Tapping an underlined item opens its summary right on the page.
- **Customizable Underline Styles**: Choose from solid, wavy, dotted, dashed, or double underlines with adjustable line thickness and contrast to suit your screen.
- **Tooltip & Footnote Displays**: Pick between a compact tooltip bubble pointing to the word or a bottom panel, along with customizable auto-close timers.
- **Frequency & Category Controls**: Highlight every mention or keep things tidy by only underlining the first appearance per chapter. You can also toggle characters, locations, terms, or historical figures independently.
- **Instant Inline Fetch Support**: When you look up and fetch a new entity while reading, it gets underlined across your book immediately.
- **Smart Matching**: Dialogue transcripts, all-caps speaker tags, and chapter headings are cleanly detected without accidental matches on common lowercase words.

### Bug fixes

- Fix #163 
- Fix #164 

*Note for users who previously installed Dukko's `2-xray-entity-footnotes.lua` patch: entity underlining is now built directly into the plugin, so the old patch file in your patches folder can be safely removed.*


**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.5...26.11.9

# 26.11.5 · 2026-11-05

This release introduces instant X-Ray lookups directly from text highlights, dedicated support for anthologies and short story collections, background unit scanning, and several performance optimizations and bug fixes.

### Instant X-Ray Popups on Highlight

You can now jump straight into X-Ray details when selecting a character, location, or term on the page, skipping intermediate dictionary popups or highlight menus.

* **Direct lookups on text selection**: When enabled, long-pressing or highlighting a word or phrase that matches an X-Ray entry immediately opens its profile or footnote popup.
* **Smart fallback**: If you select an entire sentence, an ordinary word, or text without an X-Ray entry, KOReader’s standard dictionary or highlight menu opens as usual.
* **One-tap access to the highlight menu**: When an X-Ray popup opens from a selection, a new **Highlight Menu** button appears in the action bar. Tapping it restores your text selection and opens KOReader's native highlight menu so you can create notes, highlight text, translate, or look up terms in external dictionaries without losing your place.
* **Configurable X-Ray mode setting**: Choose how X-Ray integrates with reading under *Settings* → *X-Ray Mode Settings*:
  * *Button in Menu* (Default): Classic behavior; adds an X-Ray button inside KOReader's dictionary and highlight menus.
  * *Auto-Popup on Highlight*: Displays X-Ray data instantly whenever a match is highlighted.
  * *Disabled*: Hides in-text X-Ray buttons completely.

### Anthology & Short Story Collection Support

If you read short story collections, anthologies, or omnibus editions, X-Ray now recognizes them and organizes content story by story instead of combining every character across the entire volume into one massive list.

* **Current story focus**: While reading inside a collection, characters, locations, and timeline events for *This Story* are prioritized right at the top of the menu.
* **Collapsible story sections**: Other stories in the collection are neatly organized into collapsible sections showing titles and page numbers.
* **Recurring characters across stories**: Characters who return across different stories (such as recurring detectives or companions) are tracked seamlessly across story boundaries without losing story-specific descriptions.
* **Story-aware spoiler protection**: Future story headers and their characters stay hidden until you actually reach that story in the book.

### Improvements & Fixes

* **Background unit conversions**: Unit scanning now runs asynchronously in the background so it never interrupts page turns or reader responsiveness.
* **Unit converter refinements**: Fixed recurring feature prompts and eliminated redundant scans when flipping between chapters ([#159](https://github.com/ultimatejimmy/xray.koplugin/issues/159)).
* **Timeline generation**: Fixed an issue where timeline events were not generating during full-book prefetching ([#160](https://github.com/ultimatejimmy/xray.koplugin/pull/160)).
* **Claude thinking level**: Resolved compatibility issues with newer Claude model versions and thinking level settings ([#127](https://github.com/ultimatejimmy/xray.koplugin/issues/127)).
* **Cache & disk optimizations**: Eliminated redundant cache saves and series file re-reads during background updates, noticeably improving speed on older e-ink devices ([#156](https://github.com/ultimatejimmy/xray.koplugin/issues/156)).
* **Network checks**: Addressed an issue where silent network checks could temporarily stall the UI during slow DNS lookups ([#161](https://github.com/ultimatejimmy/xray.koplugin/issues/161)).
* **List navigation**: Expanding or collapsing folded story sections on later menu pages now maintains your scroll position instead of jumping back to the first page.
* **Spoiler & prefetch reliability**: Improved spoiler protection boundaries and prefetch collision handling to keep summaries safe and downloads reliable.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.10.22...26.11.5

# 26.10.22 · 2026-10-22

This update brings offline prefetching so your X-Ray data is ready ahead of time, character history timelines that show how people and places evolve without spoiling what comes next, support for novellas and fractional book numbers in series, improved image extraction, expanded unit conversions for Cyrillic languages, and updated default AI models.

### Background Prefetch & Character Evolution

* **Offline prefetch horizon**: If you often read offline or in airplane mode, X-Ray can now quietly analyze upcoming chapters in the background while you read. You can choose how many chapters ahead to prefetch (from 1 to 5 chapters, or turned off entirely) in the settings. If you jump around the book, X-Ray automatically adjusts and prioritizes where you are.
* **Character progression and history**: You can now look back at how characters, factions, and places develop across chapters. Opening an entity card gives you access to a past evolution view showing their story arc up to your current point in the book.
* **Better handling of long sections**: Books with very long chapters or broad "Part" divisions are now broken down into smaller segments behind the scenes so prefetching stays quick and light on memory.

### Spoiler Protection

* **Strict text boundaries**: Chapter analysis now stops cleanly at chapter transitions, preventing text from future chapters from ever leaking into summaries.
* **Safer notes and highlights**: Your bookmarks and notes are only shared with the analyzer if they appear before or on your current page.
* **Clean mention previews**: Mention previews will no longer accidentally show snippets from pages ahead of where you are reading.
* **Safe backward navigation**: Going back to earlier chapters and updating X-Ray will no longer pull details from future pages into earlier summaries.

### Series & Novella Support

* **Fractional book numbering**: Series that include novellas or bridge stories (like Book 1.5 or 2.5) are now recognized and numbered accurately in timelines and series lists ([#151](https://github.com/ultimatejimmy/xray.koplugin/pull/151)) by [@tristinbaker](https://github.com/tristinbaker).
* **Better device discovery**: X-Ray now finds prior books in a series directly on your device even if you haven't opened every volume in KOReader yet.
* **Reliable series saving**: Prior book summaries are saved as they finish rather than all at once, so a network drop won't lose earlier progress.

### Book Images & Galleries

* **Faster image loading**: Image dimensions are now read directly in memory, making image browsing noticeably snappier.
* **Broader device compatibility**: Book illustration extraction now uses built-in archive tools with command-line fallbacks, ensuring image extraction and gallery viewing work reliably across Kindles, Kobos, Android, and Linux devices.

### Unit Conversions & Language Improvements

* **Written numbers in Cyrillic books**: Unit scanning now handles written numbers and ranges in Ukrainian, Russian, Serbian, and other Cyrillic languages ([#148](https://github.com/ultimatejimmy/xray.koplugin/pull/148)) by [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko).
* **Fewer false matches**: Added smarter word boundary checks to avoid accidentally turning unrelated words into units.
* **Preserved caches**: Updates to unit rules now only re-scan books in languages that were actually modified, saving battery and time.

### AI Models

* **Updated Gemini models**: Upgraded the default primary model to *Gemini 3.8 Flash* and secondary model to *Gemini 3.5 Flash Lite*.
* **Updated DeepSeek models**: Switched to active API aliases (*deepseek-flash* and *deepseek-v4-pro*).
* **Automatic migration**: Older or retired model names in your settings are automatically migrated to their modern equivalents.

### Navigation & Performance

* **Direct gesture opening**: If you map a swipe or tap gesture to open X-Ray, it now opens directly inside KOReader's main reader menu instead of a disconnected popup dialog.
* **Low-memory safeguards**: On older e-ink devices with limited RAM, background chapter scans automatically pause when memory is low to keep page turns smooth.
* **Highlight fixes**: Fixed an issue where highlights stored with alternate position markers could occasionally be missed.

### Contributors

Thanks to our contributors for their help with this release:
* [@tristinbaker](https://github.com/tristinbaker) in [#151](https://github.com/ultimatejimmy/xray.koplugin/pull/151)
* [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko) in [#148](https://github.com/ultimatejimmy/xray.koplugin/pull/148)

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.10.20...26.10.22

# 26.10.8 · 2026-10-08

This release focuses on memory optimizations and stability to keep X-Ray running smoothly, especially on older or lower-RAM e-ink devices like earlier Kindles and Kobos, along with new language support and several bug fixes.

### Memory & Performance Improvements

* **Low-memory protection**: X-Ray now monitors available device RAM. When free memory is critically low, non-essential background tasks (like automatic chapter fetches and update checks) quietly pause to prevent crashes and freezes. Manual lookups from the menu continue to work as usual.
* **Smoother book opening**: Background tasks and unit scans are deferred for a few moments after opening a book, giving KOReader room to render pages and load fonts without competing for resources.
* **Unit scanner memory cleanup**: Searching books for units now releases temporary search data in stages, noticeably reducing peak memory usage.
* **Leaner network handling**: Background network requests now clean up raw download buffers and temporary structures immediately after parsing book details.

### New Features & Improvements

* **Slovak and Czech translations**: Added Slovak and Czech language support with declension-aware lookups ([#138](https://github.com/ultimatejimmy/xray.koplugin/pull/138)) by [@misko903](https://github.com/misko903).

### Bug Fixes

* **Unit underlines**: Restored unit underlines from cache when reopening books ([#147](https://github.com/ultimatejimmy/xray.koplugin/pull/147)) by [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko).
* **Ukrainian unit conversion**: Fixed unit conversion handling for Ukrainian ([#146](https://github.com/ultimatejimmy/xray.koplugin/pull/146)) by [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko).
* Resolved issues [#143](https://github.com/ultimatejimmy/xray.koplugin/issues/143), [#144](https://github.com/ultimatejimmy/xray.koplugin/issues/144), and [#145](https://github.com/ultimatejimmy/xray.koplugin/issues/145).

### New Contributors

Thanks to our new contributors for helping improve the plugin:
* [@misko903](https://github.com/misko903) in [#138](https://github.com/ultimatejimmy/xray.koplugin/pull/138)
* [@Gargoyle-Gecko](https://github.com/Gargoyle-Gecko) in [#146](https://github.com/ultimatejimmy/xray.koplugin/pull/146)
**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.30.1...26.10.8

# 26.9.30.1 · 2026-09-30

## What's Changed
- Add gpt-6-luna support by @abs3ntdev in https://github.com/ultimatejimmy/xray.koplugin/pull/141
- ix claude bugs
- update series logic
- fix unit converter range logic
- Fix series bug
- Fix alias/lookup bug
- fix overlapping save bug


## New Contributors
* @abs3ntdev made their first contribution in https://github.com/ultimatejimmy/xray.koplugin/pull/141

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.9.30...26.9.30.1
