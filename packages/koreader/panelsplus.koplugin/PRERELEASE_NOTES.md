# v1.7.0-nightly · 2026-11-01

> “A ship in harbor is safe, but that is not what ships are built for.”
>
> — John A. Shedd

I think Panels+ is good enough as is, but what about its surrounding KOReader ecosystem?. It's time to sail beyond the horizon. Lets expand this ship (Panels+) to work together with other plugins!.

## Ink-away compatibility (in process)

<video width="100%" height="auto" src="https://github.com/user-attachments/assets/fdf3ef83-c7df-48f4-bb30-ca32a2305b90"></video>

Yep, if *Ink-Away* is installed along with Panels+, you'll be able to use Ink-away annotations while panning!, it means that all rendered annotations made by ink-reader are visible from Panels+ custom viewer, including smooth transitions and drawing outside the panel when using no-crop mode.

I'd say is 10% experimental and 90% stable, but this requires changes in ink-away internal code.

You can follow up the current state of this integration in this discussion I made to the original ink-away author:
https://github.com/EmirErtorer/ink-away.koplugin/discussions/69

Update: I've created the PR for the integration here -> https://github.com/EmirErtorer/ink-away.koplugin/pull/80


---

There are no builds so far. I need more testing for these integration features.

---

Wait? Wasn't this v1.6.0?
True, I delayed this update to v1.7.0 due to some bug reports about 1.5.1 which needed to patched (v1.6.0 Moonlight).

# v1.5.0-nightly · 2026-09-21

# The `Texty Texty` Update

This is a `Release Candidate` which means it basically is 90% done. Just I need to test it with more edge-cases and polish some features here and there, you can already test it if you want it. I doubt it could have any bugs there, its stable, so it's more about improving the new "Smart" algorithm (you'll see it in the next # Features section).

> There's no need to download these nightly versions. v1.5.0 is officially released here: https://github.com/KristanLaimon/PanelsPlus/releases/v1.5.0

## New Contributors
* @Pixxel123 made their first contribution in https://github.com/KristanLaimon/PanelsPlus/pull/7
* @MartinoAichner made their first contribution in https://github.com/KristanLaimon/PanelsPlus/pull/9
*  @IMJXXL made Chinese Simplified translation.

---

Zips:

1. `panelsplus_1_5_0_nightly_android_fix.koplugin.zip`  (Pre v1.5.0-RC1, really old)
This is a build including *D1*, *D2* and *D4* (read previous section), featuring android fix. Made to test fix for [this PR](#6) along other android bugs I found. This is an old build. Just keep for legacy concerns.

2. `panelsplus-1-5-0-RC1-OCR-EmbbededVersion.koplugin.zip`  (v1.5.0-RC1 OCR Embbeded version)
It includes all the features previously mentioned + 2 fine-tuned OCR models for spanish and english (but still compatible with your hand-installed OCR models like teserract). `4.08 MB Size`

3. `panelsplus-1-5-0-RC1.koplugin.zip` (v1.5.0-RC1)
It includes all the features previously mentioned only without embbeded fine-tuned models (but still compatible with your hand-installed OCR models like teserract). `183 KB`

# v1.4.0-nightly · 2026-09-06

Hello fellas, this time, it's a nightly build release. Including some fixes for bugs found thanks to @sukhmeetsingh170200 and other ones I found myself and translations!. Why not a full release? well, normally I test the plugin many days myself until I found it stable and pleasant to use but wanted to release these meanwhile I'm battle-testing this 1.4.0 version. 

## Features
- Added native spanish translations for my spanish users.

## Enhancements 
- Improved flow layout order when reading in comic and manga mode, should follow panels from top to bottom and (left to right | comicmode) and (right to left | mangamode) going from upper panel to upwards direction instead of upwards.

## Fixes
- Fixed [strange device orientation behaviour](#1) when using Panels+ orientation then for some reason going back to original Koreader orientation.
- Many other fixes that are too technical and I'm lazy to document.I'll document them properly in the future 1.4.0 stable release.


# Notes:
This version is not battle-tested as normal stable-versions, use this nightly build if you want to test-out the latest features without having to wait for the next stable release.

If you're openning an issue make sure you're using the [latest stable version instead](https://github.com/KristanLaimon/PanelsPlus/releases/latest)
