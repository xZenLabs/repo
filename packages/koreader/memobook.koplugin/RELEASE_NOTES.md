# v1.3.0

### MemoBook v1.3.0
- **Rename a memo** — Hold a memo in the Memo Book list and tap Rename to change its main word; notes and aliases stay with it, a word another memo in the book already uses is refused, and an alias of the memo itself simply becomes the new main word.

- **Create a memo by hand** — The new New memo control in the list (also offered when the list is still empty, where there was previously no way in) asks for a word and opens the usual memo pop-up on it, so a memo no longer has to start from a highlight; an existing word opens its memo instead of duplicating it.

- **Fixed: the Memo button disappeared from the dictionary pop-up** — The button was registered without a menu label, so KOReader's "Customize buttons" selector never listed it and silently dropped it from the saved layout the first time you sorted or toggled anything there; it is now listed, and the missing button is restored once on upgrade.

# v1.2.0

- show multiple notes as a scrollable list instead of buttons
- remove alias by tapping it in a scrollable list
- attach a selection to an existing memo as an alias

# v1.1.0

- support new KOReader dict API (PR #15184) with fallback to legacy hook

# v1.0.3

- fix: note not shown on alias

# v1.0.2

- document id added on export json
