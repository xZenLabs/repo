# v1.5.0-nightly

This is the road-map for next update which I'm planning to name `Texty-Texty`, being the main focus to improve OCR for dictionary-lookups and translations and all text-features related to mangas/comics.


# v1.5.0-BETA Features Implemented so far

D1 = Done 1,  D2 = Done 2 and so on.

## D1 @Pixxel123 [\[Pull Request\]](#2): Panels+ new trigger with double finger tab instead of always long press
 In case you have other plugins that uses the Long-press gestures in your panels, (opt-in option).  

https://github.com/user-attachments/assets/46cfb6a1-3f66-48fc-a8eb-0ecc5a7a6921

---

## D2 @MartinoAichner [\[Pull Request\]](https://github.com/KristanLaimon/PanelsPlus/pull/9): Improved OCR recognition for PDF files that include a text-layer embbeded.

<img width="800" height="450" alt="text_layer_before_ocr" src="https://github.com/user-attachments/assets/2a72596c-efb5-48bc-9d1c-caa8eb33b2d4" />
<em>Showcase made by @MartinoAichner</em>

--- 

## D3 @KristanLaimon [Generic Feature]: Increased panel recognition patterns by adding more common mangas to internal Panels+ dataset like:
- [Nagatoro (Vol. 1)](https://es.wikipedia.org/wiki/Ijiranaide,_Nagatoro-san)
- [Horimiya (Vol 1.)](https://es.wikipedia.org/wiki/Hori-san_to_Miyamura-kun)
Which means, this plugin will have at least 95% precision on those mangas natively and will improve panels finding in other mangas as collateral effect (the purpose for this).

---

## D4 @KristanLaimon [(Bug-fix, reported by @Keithcat25)](https://github.com/KristanLaimon/PanelsPlus/issues/6): Fixed bad rotation bug in android devices
Before:
<table>
  <tr>
    <td width="33%">
      <img alt="Image" src="https://github.com/user-attachments/assets/abe26e27-ef2f-402c-a867-d13e369a1b5d" />
    </td>
    <td width="33%">
      <img alt="Image" src="https://github.com/user-attachments/assets/13b4662d-414d-4d56-92cf-b42439289e02" />
    </td>
    <td width="33%">
      <img alt="Image" src="https://github.com/user-attachments/assets/f02e3046-8470-4a0b-9aa2-1405f4217eee" />
    </td>
  </tr>
</table>
<em>Images/Feedback provided thanks to @Keithcat25</em>


After:
<video alt="Image" src="https://github.com/user-attachments/assets/86a7a166-557d-4354-9754-2f90e7339e66" />

<em>Showcase made by <strong>me</strong></em>

---

# v1.5.0 ToDo: 
- [(Opt-in Option) to recognize whole phrases for traductions, suggestion from a PR](https://github.com/KristanLaimon/PanelsPlus/pull/9)
- [Have better support for double page illustrations (divided in 2 pages, and in 1 page variants)](#5), currently being developed in [this PR](https://github.com/KristanLaimon/PanelsPlus/pull/10).
- Remove animation transition bug in text-based formats (.epub, .mobi, etc...) when changing of pages (not related to Nav. Animated)
- Add Nav.Animated transitions while dark mode.

---

## New Contributors
* @Pixxel123 made their first contribution in https://github.com/KristanLaimon/PanelsPlus/pull/7
* @MartinoAichner made their first contribution in https://github.com/KristanLaimon/PanelsPlus/pull/9

---

# Nightly Builds

1. `panelsplus_1_5_0_nightly_android_fix.koplugin.zip`
This is a build including *D1*, *D2* and *D4* (read previous section), featuring android fix. Made to test fix for [this PR](#6) along other android bugs I found.

If you want to have all D# like features, you can follow the [build instructions](https://github.com/KristanLaimon/PanelsPlus#%EF%B8%8F-building-from-source) to test this unreleased v1.5 features, not guaranteed to be stable though due to the Nightly builds nature, but you will have all the cutting edge features from Panels+!

# v1.4.0-nightly

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
