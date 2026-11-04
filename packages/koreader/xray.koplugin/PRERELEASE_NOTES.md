# 26.11.4-beta2 · 2026-11-04

- Do unit scanning in the background 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.2-beta...26.11.4-beta2

# 26.11.4-beta · 2026-11-04

- Improve spoiler mode logic
- Improve pre-fetch/collision logic

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.2-beta...26.11.4-beta

# 26.11.2-beta · 2026-11-02

- Address network check potential issue: #161 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.10.28-beta...26.11.2-beta

# 26.10.28-beta · 2026-10-28

### New Features

* **Anthology and Short Story Collection Support**: If you read short story collections, anthologies, or omnibus editions, X-Ray now recognizes them and organizes everything story by story instead of dumping every character across the entire volume into one massive list.
  * **Current Story Focus**: While reading inside a collection, the characters, locations, and timeline events for *This Story* are highlighted right at the top of the menu.
  * **Collapsible Story Sections**: Other stories in the collection are neatly folded into collapsible sections, showing page numbers and story titles.
  * **Recurring Characters Across Stories**: Characters who return across different stories (such as recurring detectives or companions) are tracked seamlessly across story boundaries without losing story-specific descriptions.
  * **Story-Aware Spoiler Protection**: Future story headers and their characters stay hidden until you reach that story in the book, matching your spoiler settings.

### Improvements & Fixes
- Fix issue with new claude version and thinking level #127 
* **Timeline **: Fixed an issue where timeline wasn't generating on a full-book prefetch #160 
* **List Navigation**: Toggling folded story sections on later pages of the menu now preserves your position instead of jumping back to page one.
* **Unit Converter Refinements**: Improved the new feature prompt behavior and eliminated redundant background unit scans when navigating between chapters. #159 
* Fix #156 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.10.22...26.10.28-beta

# 26.10.23-beta · 2026-10-22

## What's New

### Instant X-Ray Popups on Highlight

You can now jump straight into X-Ray details when selecting a character, location, or term on the page, skipping the intermediate dictionary popup or highlight menu.

* **Direct Lookups on Text Selection:** When enabled, long-pressing or highlighting a word or phrase that matches an X-Ray entry immediately opens its profile or footnote popup.
* **Smart Fallback:** If you highlight an entire sentence, a phrase without X-Ray data, or an ordinary word, KOReader's standard dictionary or highlight menu opens just like before.
* **One-Tap Access to the Highlight Menu:** Whenever an X-Ray popup opens from a highlight, a new **Highlight Menu** button appears in the action bar. Tapping it restores your text selection and opens the native KOReader highlight menu so you can still create notes, highlight passages, translate, or check external dictionaries without losing your place.
* **New X-Ray Mode Setting:** Choose how X-Ray integrates with reading under **Settings → X-Ray Mode Settings**:
  * **Button in Menu (Default):** Keeps the classic behavior, adding an *X-Ray* button inside KOReader's dictionary and highlight menus.
  * **Auto-Popup on Highlight:** Skips the menu and displays X-Ray data instantly when a match is found.
  * **Disabled:** Hides in-text X-Ray buttons completely.

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.10.22...26.10.23-beta
