# v0.2.5 · 2026-11-23

This update adds a cancel button to the search. In case you want to cancel a long running search you can press it and exit the search  process early on. The plugin will quit on cancel.

# v0.2.4 · 2026-10-09

Correctly switch to next mirror if unavailable, fix error message.

This release changes to the next mirror of LibGen when the current one is unavailable. Additionally the error messages reported on failure are improved.

Thanks to @prBigBrother for the help.

# v0.2.3 · 2026-10-02

This update adds relevance sorting to the search results.

The fallback implemented in the last version doesn't natively support sorting of the results so its added in this version on device.

# v0.2.2 · 2026-09-28

Fix No results with direct Libgen fallback.
Adds direct Libgen fallback when Anna is gone.

Since the DDoS guard seems to stay with us for a while the plugin will now directly search Libgen for queries. While the original implementation would look for results from different hosts, most files should be available on Libgen as well.

Note that search filters might not work as well as on Annas.

Also added Czech and Slovak language filters.

# v0.2.0 · 2026-08-13

This update separates the underlying code forked from the ZLibrary KOReader plugin and fixes issues with invalid server response handling:


Fixes compatibility issues when both ZLibrary and Annas plugin are installed.
Fixes issue where language filter is ignored. Thanks to @LaiKash
Fixes issue where format filter is ignored.
Fixes issue where format of search result is not shown.


Please note that the associated plugins dispatcher action was renamed in this process, which might lead to your saved gestures / shortcuts connected to this plugin to be silently deleted. Please check and rebind them to this plugin.

**Full Changelog**: https://github.com/fischer-hub/annas.koplugin/compare/v0.1.8...v0.2.0
