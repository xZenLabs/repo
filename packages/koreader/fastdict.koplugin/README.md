# FastDict — instant dictionary lookups for KOReader

Answers exact-word dictionary lookups in-process instead of spawning a
`sdcv` process per lookup. This avoids sdcv 0.5.5's full linear re-scan of
`.syn` files on every launch — with a 46 MB / 1.7M-entry inflection `.syn`
that scan alone costs seconds per tap on an e-reader.

## What it does

- Hooks `ReaderDictionary.rawSdcv`. Exact (tap-on-word) lookups are served
  by a pure-Lua StarDict engine: binary search over `.idx`/`.syn` using
  sidecar offset caches (`.fdx` files, built once per dictionary), with
  dictzip chunks decompressed on demand via zlib FFI.
- Fuzzy ("similar words") search, special query syntax (`*?\/|`),
  unsupported dictionaries, and any engine error fall back to the original
  sdcv path automatically. Lookups can never break, only speed up.
- On an exact hit, results are byte-identical to `sdcv --exact-search` output
  (verified by `test/parity.py` against sdcv 0.5.5). On an exact **miss**, the
  engine retries a few cheap English base-form candidates (`streets → street`,
  `studies → study`, `walked → walk`, `running → run`) so inflected words still
  resolve without turning on the slow fuzzy search. Only candidates that hit a
  real headword are used, so this never invents results; irregular forms
  (`went → go`) still need fuzzy search.

## Install (Kindle)

1. Download **`fastdict.koplugin.zip`** from the
   [latest release](https://github.com/asxelot/fastdict.koplugin/releases/latest)
   and unzip it. It expands to a correctly-named `fastdict.koplugin/` folder —
   no renaming needed.
2. Copy that folder to `/mnt/us/koreader/plugins/fastdict.koplugin/`.
3. Restart KOReader.
4. Optional: menu → Search → FastDict → "Build index caches now"
   (otherwise caches build on the first lookup; a one-time few-second wait
   for very large dictionaries).

<details>
<summary>Install from source instead</summary>

`git clone` this repo (or **Code → Download ZIP** and unzip, then strip the
`-main` suffix so the folder ends in `.koplugin`). Only `_meta.lua`,
`main.lua`, `engine.lua`, `stardict.lua` and `dictzip.lua` are needed at
runtime.
</details>

## Not supported by the engine (served by sdcv instead)

- `sametypesequence` with multiple types, resources, or 64-bit offsets
- `.idx.gz` compressed indexes
- fuzzy/regex/data queries

## Companion tool

`tools/merge_syn.py` folds a `.syn` into the `.idx` offline (run on a PC),
which also makes the sdcv fallback path fast for fuzzy searches:

    python3 tools/merge_syn.py <dict_dir> <out_dir>

## Tests (desktop)

    python3 test/make_fixture.py /tmp/fastdict-fixture
    luajit test/run_tests.lua /tmp/fastdict-fixture
    python3 test/parity.py <dicts_copy_dir> <sdcv-binary> <luajit-binary>
