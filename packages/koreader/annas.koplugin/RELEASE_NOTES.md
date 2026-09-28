# v0.2.2

Fix No results with direct Libgen fallback.
Adds direct Libgen fallback when Anna is gone.

Since the DDoS guard seems to stay with us for a while the plugin will now directly search Libgen for queries. While the original implementation would look for results from different hosts, most files should be available on Libgen as well.

Note that search filters might not work as well as on Annas.

Also added Czech and Slovak language filters.

# v0.2.0

This update separates the underlying code forked from the ZLibrary KOReader plugin and fixes issues with invalid server response handling:


Fixes compatibility issues when both ZLibrary and Annas plugin are installed.
Fixes issue where language filter is ignored. Thanks to @LaiKash
Fixes issue where format filter is ignored.
Fixes issue where format of search result is not shown.


Please note that the associated plugins dispatcher action was renamed in this process, which might lead to your saved gestures / shortcuts connected to this plugin to be silently deleted. Please check and rebind them to this plugin.

**Full Changelog**: https://github.com/fischer-hub/annas.koplugin/compare/v0.1.8...v0.2.0

# v0.1.8

## What's Changed
* Fix bugs and crashes (make this work again) by @ThePixelPro366 in https://github.com/fischer-hub/annas.koplugin/pull/4
* Fix: Resolved Crash caused by FBI killing Domain, changed scraping to… by @DerSchmachtin in https://github.com/fischer-hub/annas.koplugin/pull/5

## New Contributors
* @ThePixelPro366 made their first contribution in https://github.com/fischer-hub/annas.koplugin/pull/4
* @DerSchmachtin made their first contribution in https://github.com/fischer-hub/annas.koplugin/pull/5

**Full Changelog**: https://github.com/fischer-hub/annas.koplugin/compare/v0.1.7...v0.1.8

# v0.1.7

This update fixes an issue causing crashes when AA is not responding.

# v0.1.6

This update fixes issues with the version number in the packaging.
