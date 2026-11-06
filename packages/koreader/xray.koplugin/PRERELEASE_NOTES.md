# 26.11.6-beta · 2026-11-06

Fix #163 

**Full Changelog**: https://github.com/ultimatejimmy/xray.koplugin/compare/26.11.5...26.11.6-beta

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
