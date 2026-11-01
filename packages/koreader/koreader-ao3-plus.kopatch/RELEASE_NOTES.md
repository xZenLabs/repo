# 1.1.1 · 2026-11-01

Fixes:
- %ao3_review could wrap onto a second list line when the saved note's
  first line was long, since Bookshelf 6.1.1 lets any line wrap into
  spare row height. The token now caps its output at 60 UTF-8
  characters, trimming to the last whole word and appending an
  ellipsis so it reliably renders as a single list line.
- Renamed the token's description to "review snippet" to reflect that
  it is now a shortened preview rather than the untruncated first line.

# 1.1.0 · 2026-11-01

Fixes:
- Restructured the scanner into two layered sources: Ao3 subject metadata
  (dc:subject tags in the EPUB's OPF) is read first for rating, category,
  warning, fandom, relationships and tags. Whenever any of those come up
  empty - for example, a conversion tool stripped the metadata - the
  scanner now also reads the same fields directly from the EPUB's own Ao3
  preface page instead, so badges and fandom no longer disappear for
  non-standard EPUBs.

New:
- New Bookshelf tokens: %ao3_pairing (first relationship), %ao3_tags
  (scanned Additional Tags, optional replacement for %genres), %ao3_updated
  (Ao3's Completed date for finished multi-chapter works, Updated for
  works still in progress, or Published for one-shots), %ao3_review
  (your own review, first line), %ao3_review_full (your own review, in
  full).
- Detailed list: new Pairing line under Fandom, and the
  Completed/Updated/Published date added to the fic-data line next to
  Words/Chapters.
- New "Use scanned Additional Tags instead of genres" setting for the
  detailed list's tags line (off by default).
- New display toggles: Show pairing and Show updated date.

# 1.0.2 · 2026-10-19

Fix: Changed source for fandom scan from tags to epub pages.

Added new tokens:
- `%ao3_fandom`: Only the first fandom, as it did before 1.0.2
- `%ao3_multifandom`: All fandoms, separated by commas

# 1.0.1 · 2026-10-16

Fix: badges glitch when tapped to open in top panel.

# 1.0.0 · 2026-10-16
