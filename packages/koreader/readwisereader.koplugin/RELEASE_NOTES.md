# v2.6 · 2026-10-12

* Use Readwise v3 API to attach highlight to original Reader Documents https://github.com/Endle/readwisereader/issues/20
* Add cover to each sync'ed document (Thanks @Kageetai)

Sync cover is disabled by default. To enable it, Settings->Image Download->Download article covers

# v2.5 · 2026-08-28

Implemented "Advanced Sync"

Allowing to only export highlights to Readwise, instead of full synchronizing.

# v2.4 · 2026-01-26

Add source_url to highlight exports for better Readwise linking 
Map site_name to KOReader series field for filtering
Add location-based collection management 
Fixes "attempt to index field 'ui' (a nil value)" crash

# v2.3 · 2026-01-16

Adds a function where (optionally) the plugin will only sync articles tagged 'koreader".
Also, improves the syncing process, so that tag changes and article deletions on the Readwise server are replicated in KoReader.
Fixes the progress messages stacking up during the sync and simplifies the message lifecycle management.
Improved document file handling
Improved handling of image size limit
Refactor article synchronisation logic
Add metadata sidecar file support

# v1.7 · 2025-12-04

Adds a new function in which users can limit the number of downloaded articles. 
With thanks to @nimarb
