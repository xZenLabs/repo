# Solar Icon Packs for ZenOS

Modern, rounded replacement icons for [ZenOS](https://github.com/xZenLabs/zen-os), packaged by [ZenLabs](https://github.com/xZenLabs) from the original [Solar Icon Pack by pxlflux](https://github.com/pxlflux/solariconpack.koplugin).

## Icon overviews

### Solar Colour

![Solar Colour: selected KOReader controls, library tabs, and common actions](.github/overview-solar-colour.png)

### Solar Mono

![Solar Mono: selected KOReader controls, library tabs, and common actions](.github/overview-solar-mono.png)

## What's included

Each style contains 421 SVG files named for ZenOS, KOReader, and ZenPM's exact icon lookups, including all 102 original KOReader filenames and drawings. Every lookup is an editable source file, including names previously generated as aliases during the build. Matching grids and line weights keep the artwork consistent across the three interfaces. Missing icons use the bundled artwork.

| Pack | Style | Made for | Release asset |
|---|---|---|---|
| **Solar Colour** | Soft pastel fills, 0.75 stroke | Colour e-ink screens | `zen-solar-colour.zip` |
| **Solar Mono** | Bolder outlines, 1.0 stroke | Black & white e-ink screens | `zen-solar-mono.zip` |

The additional designs cover battery levels and charging, calculator, CPU, database, compass, folders, USB, sharing, timer, warmth, sun, playback controls, dictionary, highlighting, and other shipped utilities. Restart, Bluetooth, incognito, lockdown, the app launcher, and Zen mode are included in both styles.

All 23 built-in choices under **Navbar → Tabs → Add → Tab** have themed icons. Key mappings are:

| Tab | ZenOS filename | Artwork |
|---|---|---|
| Library / Kindle Library | `library.svg` | Books on a shelf |
| Series | `tab_series.svg` | Horizontal stack of books |
| Stats | `tab_stats.svg` | Progress chart |
| Languages | `tab_translate.svg` | Globe |
| Tags | `tab_tags.svg` | Tag |
| News | `tab_news.svg` | Article |
| Folder | `tab_folder.svg` | Folder |
| Archive | `archive.svg` | Archive box |

Calibre and `tab_books.svg` share the Library artwork. Reading progress uses `quick_stats_progress.svg`; the statistics calendar retains its calendar icon. Battery SVGs are available for controls and icon selection; ZenOS's status-bar battery indicators and other inline font glyphs use their existing font artwork.

ZenPM's KOReader frontend is covered in both styles: all 39 bundled SVG names
and 33 inline menu names (63 unique lookups). This includes navigation, all 12
categories, package and queue actions, verification badges, source icons, search,
filtering, sorting, and settings. ZenPM must support the selected ZenOS icon pack
for these replacements to appear; older frontends that load bundled icons and
font glyphs directly keep their original artwork. Downloaded package logos and
previews retain their own artwork.

Chess, Notion, and RSS now use pxlflux v1.1.0 artwork, along with refreshed launcher,
dictionary, palette, trash, and utility icons. Connections and unmatched lookup
actions keep the bundled artwork. The carousel icon is rotated 90 degrees clockwise. The additions come from the [official Solar Icon Set](https://github.com/480-Design/Solar-Icon-Set/tree/44017167688b49109d88ae6a98979b23d8950db0/icons/SVG/Bold); source names and adaptation details are recorded in [icon attribution](LICENSE-ICONS.txt).

Reader controls include `pin.svg`, `footnote.svg`, `return.svg`, and the
compatible `return_old.svg` lookup, alongside the highlight style, color,
delete, filter, and sort icons.

Page-browser and reader-control lookups include `annotations.svg`,
`bookmark_outline.svg`, `document.svg`, `page.svg`, `profiles.svg`,
`moon_outline.svg`, `history.svg`, and zoom and fullscreen controls.
`pin_remove.svg` and `bookmark_remove.svg` draw a line through the pack's own
pin and bookmark. Settings rows also cover the copy, cut, paste, sort, sync,
and other `settings_*` lookups used by ZenOS context menus.

## Install with ZenPM

1. Open [ZenPM](https://github.com/xZenLabs/zen-pm) in KOReader. If it isn't installed, use **Zen Settings → Extras → Install ZenPM** on supported devices, or follow the [ZenPM installation guide](https://github.com/xZenLabs/zen-pm/blob/main/docs/installation.md).
2. Refresh ZenPM's sources, then open **Categories → Icon Packs** and select the Solar icon pack.
3. Choose `zen-solar-colour.zip` or `zen-solar-mono.zip`, select **Install**, and confirm any queued changes in **Queue**.
4. If ZenPM offers to activate the pack, choose **Use icon pack** (or your preferred pack if you installed both), then restart KOReader. You can also select it under **Zen Settings → Interface → Custom icons → Custom icon pack**, with **Custom icons** enabled.

If **Icon Packs** or Solar is unavailable in your ZenPM catalog, use the manual installation below.

## Manual install for ZenOS

1. Download `zen-solar-colour.zip` or `zen-solar-mono.zip` from [this repository's latest release](https://github.com/xZenLabs/solariconpack-zen/releases/latest).
2. Copy the ZIP into `koreader/icons/zen/` on your device. Create the folders if needed.
3. Open **Zen Settings → Interface**, enable **Custom icons**, then open **Custom icons → Custom icon pack** and choose **Solar Colour for ZenOS** or **Solar Mono for ZenOS**. ZenOS validates and unpacks the ZIP automatically.
4. Restart KOReader to apply the pack.

You can also extract the ZIP yourself and copy its `zen-solar-colour` or `zen-solar-mono` folder into `koreader/icons/zen/`. Keep `pack.json` and the SVG files directly inside that pack folder.

For more details, see the [ZenOS custom icon pack guide](https://github.com/xZenLabs/zen-os/blob/main/docs/icon-packs.md).

### Switching or removing a pack

Choose another pack under **Zen Settings → Interface → Custom icons → Custom icon pack** and restart KOReader. To restore the default artwork, disable **Custom icons** and restart.

After switching away from a pack, remove it through ZenPM if ZenPM installed it, or delete its folder from `koreader/icons/zen/` if you installed it manually.

## Building the ZenOS packs

For your own pack, start with the [Zen icon pack template](https://github.com/xZenLabs/icon-pack-template).

### Source layout

Each style keeps category folders directly beside `pack.json`.
Categories without replacement artwork can be absent:

```text
<Style>/
├── pack.json
├── navbar/
├── controls/                 # Quick settings and Zen controls
├── launcher/
├── zenpm/                    # Includes verification shields
├── lookup/
├── menus/                    # Zen menu entry points
├── reader/                   # Page browser: TOC, vocabulary, view modes
├── device/
├── settings/                 # Zen settings menu rows
└── koreader/                 # Stock KOReader icons, including plus/info
```

[ICON-LIST.md](ICON-LIST.md) lists the filenames by category. Page-browser TOC, vocabulary-builder,
and view icons belong in `reader/`. All stock KOReader icons, including `appbar.*`,
the Aa font button, plus/info, bookmarks, and `book_open`, belong in `koreader/`. Quick settings
belong in `controls/`; `tab_left` and `tab_right` belong in `navbar/`.
Shared lookup names appear only once per style;
different lookup names can be edited independently.

Legacy SimpleUI `qa_group` and `qa_plugin` files are omitted. ZenPM uses
`plugin.svg`; its verification shields belong in `zenpm/`.
The builder flattens the categories into the pack root in release ZIPs,
so installed lookup names and artwork remain unchanged apart from the two
obsolete SimpleUI names. Missing icons keep their normal bundled fallbacks.

### Build and validate

Each pack manifest includes `"color": true` for colour artwork or
`"color": false` for monochrome artwork. Per-style values are retained in the
release ZIPs when building the whole repository.

The source SVGs already use their runtime lookup names; the packs have no Lua
scripts. The builder recursively gathers each style's category folders,
validates the assets, and creates both release ZIPs. Install its
dependency, then run it with Python 3:

```sh
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install -r scripts/requirements.txt
python3 scripts/build-zen-packs.py
```

Regenerate the Navbar and utility contact sheets in `dist/` with one icon per
cell and exact lookup names:

```sh
python3 scripts/build-previews.py
```

Preview rendering requires `rsvg-convert` from librsvg. It renders the existing
SVG artwork directly; the pack ZIP build does not need this tool.

To build just one style, pass `"Solar Colour"` or `"Solar Mono"` as the source.
The builder's SimpleUI mappings remain available for other extracted packs:

```sh
python3 scripts/build-zen-packs.py /path/to/NightOwl --output dist --version 1.0.0
python3 -m unittest discover -s scripts -p 'test_*.py'
```

Point it at a pack with category folders beside `pack.json`, a flat pack folder, a folder
containing several packs, or a legacy repository with `Pack Icons`, `KOReader Icons`, and supplementary icon
folders. Extract ZIP inputs first. Optional `pack.lua` metadata and filename mappings are read as
literal quoted strings without running Lua; computed Lua values are unsupported.
Without Lua metadata, standard `sui_*` SVG/PNG filenames are translated to ZenOS
names. Existing canonical icons take priority, and partial packs are supported.
Root `pack.json` is the shared metadata source for automated builds, including
schema version, version, and author; per-style manifests supply metadata when
building a style directly. When building several packs, each pack gets its own
ID and name from legacy `pack.lua` metadata or its folder name; a single pack
uses root `pack.json`'s ID and name directly. Without root
metadata, `pack.lua` supplies the available version and author. `--version`
overrides the manifest version for release builds.

The build validates SVG documents and ZenOS ZIP limits, checks archive integrity,
and writes the packs to the output directory. Each ZIP contains one folder
matching its `pack.json` ID and retains available source licences, including
[icon attribution](LICENSE-ICONS.txt).

Every PNG is verified, decoded, and encoded as a new RGBA PNG containing only
pixels. Text, EXIF, ICC profiles, private chunks, and appended files are discarded;
transparency is retained. Invalid, oversized, and animated PNGs fail the build.
This strips non-pixel payloads; it cannot detect data encoded in the pixels and
does not guarantee that an image decoder has no vulnerabilities. SVG artwork is
validated but is not rewritten or sanitised.

The release workflow runs on pushes to `main` and manually through **Actions →
Release Zen icon packs → Run workflow**. When a push increases root `pack.json`'s
version above its value on `main` before that push, the workflow releases that
exact version. Otherwise, including manual workflow runs, it increments the patch
number above the higher of root `pack.json` and existing `vMAJOR.MINOR.PATCH` tags.
For example, a manual change from `1.2.0` to `1.3.0` releases `v1.3.0`;
an unchanged manifest with latest tag `v1.3.0` releases `v1.3.1`.
Release runs are serialized to avoid duplicate tags.
The workflow builds and validates all packs with the selected version, then
creates the tag on the triggering commit and publishes the generated ZenOS ZIPs.

## Credits and licence

- **Original repository:** [pxlflux/solariconpack.koplugin](https://github.com/pxlflux/solariconpack.koplugin). pxlflux adapted the Solar artwork for KOReader, recoloured the Colour version, refined the Mono outlines, and drew additional icons.
- **Original icon set:** [Solar Icon Set](https://www.figma.com/community/file/1166831539721848736) by **480 Design**, licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- **ZenOS packaging:** [ZenLabs](https://github.com/xZenLabs) preserves the original SVG artwork, adapts additional Solar designs to both pack styles, and supplies grouped source SVGs using ZenOS and ZenPM lookup names.
- The icons remain under **CC BY 4.0**. See [LICENSE](LICENSE) and [LICENSE-ICONS.txt](LICENSE-ICONS.txt).

## Support and funding

Feedback and icon requests are welcome: open an [issue in this repository](https://github.com/xZenLabs/solariconpack-zen/issues).

Support ZenOS and the ZenLabs projects through [ZenLabs on Ko-fi](https://ko-fi.com/xzenlabs). Contributions help fund ongoing development and maintenance.
