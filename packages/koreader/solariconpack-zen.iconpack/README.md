# Solar Icon Packs for ZenOS

Modern, rounded replacement icons for [ZenOS](https://github.com/xZenLabs/zen-os), packaged by [ZenLabs](https://github.com/xZenLabs) from the original [Solar Icon Pack by pxlflux](https://github.com/pxlflux/solariconpack.koplugin).

<img width="2400" height="1180" alt="Solar Icon Pack: Colour and Mono icons" src="https://github.com/user-attachments/assets/60011e18-b307-41fd-b141-17c4e2a54f58" />

## What's included

Each pack includes all 160 source icons plus filename aliases for ZenOS's Navbar, Controls, and supported lookup actions. Matching grids and line weights keep the artwork consistent across ZenOS and KOReader. Missing icons use the bundled ZenOS and KOReader artwork.

| Pack | Style | Made for | Release asset |
|---|---|---|---|
| **Solar Colour** | Soft pastel fills, 0.75 stroke | Colour e-ink screens | `zen-solar-colour.zip` |
| **Solar Mono** | Bolder outlines, 1.0 stroke | Black & white e-ink screens | `zen-solar-mono.zip` |

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

## Full icon list

<details>
<summary><strong>Solar Colour</strong></summary>

![Solar Colour: every icon with its filename](Solar%20Colour/Full%20Icon%20Overview%20%28Colour%29.png)

</details>

<details>
<summary><strong>Solar Mono</strong></summary>

![Solar Mono: every icon with its filename](Solar%20Mono/Full%20Icon%20Overview%20%28Mono%29.png)

</details>

## Building the ZenOS packs

Install the build dependency, then build both release ZIPs with Python 3:

```sh
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install -r scripts/requirements.txt
python3 scripts/build-zen-packs.py
```

The builder also works with other extracted SimpleUI packs:

```sh
python3 scripts/build-zen-packs.py /path/to/NightOwl --output dist --version 1.0.0
python3 -m unittest discover -s scripts -p 'test_*.py'
```

Point it at a flat pack folder, a folder containing several packs, or a repository
with `Pack Icons`, `KOReader Icons`, and supplementary icon folders. Extract ZIP
inputs first. Optional `pack.lua` metadata and filename mappings are read as
literal quoted strings without running Lua; computed Lua values are unsupported.
Without a manifest, standard `sui_*` SVG/PNG filenames are translated to ZenOS
names. Existing canonical icons take priority, and partial packs are supported.
Root `pack.json` is a complete manifest example and the shared metadata source
for builds, including schema version, version, and author. When building several
packs, each pack gets its own ID and name from `pack.lua` or its folder name;
a single flat pack uses root `pack.json`'s ID and name directly. Without root
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
Release Zen icon packs → Run workflow**. It increments the patch number above
the higher of root `pack.json`'s version and existing `vMAJOR.MINOR.PATCH` tags
(for example, `1.0.0` → `v1.0.1` → `v1.0.2`). Update root `pack.json` to set a
new major or minor baseline. Release runs are serialized to avoid duplicate tags.
The workflow builds and validates all packs with the selected version, then
creates the tag on the triggering commit and publishes the generated ZenOS ZIPs.

## Credits and licence

- **Original repository:** [pxlflux/solariconpack.koplugin](https://github.com/pxlflux/solariconpack.koplugin). pxlflux adapted the Solar artwork for KOReader, recoloured the Colour version, refined the Mono outlines, and drew additional icons.
- **Original icon set:** [Solar Icon Set](https://www.figma.com/community/file/1166831539721848736) by **480 Design**, licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- **ZenOS packaging:** [ZenLabs](https://github.com/xZenLabs) preserves the source SVG artwork and adds filename aliases for ZenOS's controls.
- The icons remain under **CC BY 4.0**. See [LICENSE](LICENSE) and [LICENSE-ICONS.txt](LICENSE-ICONS.txt).

## Support and funding

Feedback and icon requests are welcome: open an [issue in this repository](https://github.com/xZenLabs/solariconpack-zen/issues).

Support ZenOS and the ZenLabs projects through [ZenLabs on Ko-fi](https://ko-fi.com/xzenlabs). Contributions help fund ongoing development and maintenance.
