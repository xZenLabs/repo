# v1.0.0

First release.

Instant dictionary lookups for KOReader: answers exact-word (tap-on-word) lookups in-process with a pure-Lua StarDict engine instead of spawning `sdcv` per lookup, avoiding sdcv 0.5.5's full linear `.syn` re-scan on every tap. Fuzzy search, special queries, and any engine error fall back to sdcv automatically, so lookups can never break — only speed up. Exact hits are byte-identical to `sdcv --exact-search`.

### Install (Kindle)
Download `fastdict.koplugin.zip` below and unzip it — it expands to a correctly-named `fastdict.koplugin/` folder. Copy that to `/mnt/us/koreader/plugins/fastdict.koplugin/` and restart.
