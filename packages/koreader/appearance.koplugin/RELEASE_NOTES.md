# v1.10.0 · 2026-11-28

## [1.10.0](https://github.com/Euphoriyy/appearance.koplugin/compare/v1.9.0...v1.10.0) (2026-11-28)
[![Github Downloads (by release)](https://img.shields.io/github/downloads/Euphoriyy/appearance.koplugin/v1.10.0/total.svg)](#)


## Features

* **misc:** add system theme detection on desktop ([6e58de7](https://github.com/Euphoriyy/appearance.koplugin/commit/6e58de7))
* **ui/accent_color:** add option to tint icons with the accent color ([1cccddc](https://github.com/Euphoriyy/appearance.koplugin/commit/1cccddc))
* **ui/background_color:** disable icon inversion options only while icons are tinted ([baace0e](https://github.com/Euphoriyy/appearance.koplugin/commit/baace0e))
* **ui:** add text editor font customization ([27e06e1](https://github.com/Euphoriyy/appearance.koplugin/commit/27e06e1))
* **ui:** add virtual keyboard font customization ([50cc16a](https://github.com/Euphoriyy/appearance.koplugin/commit/50cc16a))
* **book/background_color:** apply to alt status bar ([16cef45](https://github.com/Euphoriyy/appearance.koplugin/commit/16cef45))

## Bug Fixes

* **colorwheelwidget:** prevent window movement when panning on Android ([67ffc96](https://github.com/Euphoriyy/appearance.koplugin/commit/67ffc96))
* **android:** add partial workaround for inverted rounded corners in night mode ([a9c0bc8](https://github.com/Euphoriyy/appearance.koplugin/commit/a9c0bc8))
* **linux:** handle all portal color-scheme values correctly, falling back to GNOME/KDE settings when no preference is specified ([9f9fa99](https://github.com/Euphoriyy/appearance.koplugin/commit/9f9fa99))
* **ui:** use valid foreground color variable for keyboard borders ([29a2f04](https://github.com/Euphoriyy/appearance.koplugin/commit/29a2f04))
* **themes:** fix editing and deleting the wrong theme when names collide ([411e378](https://github.com/Euphoriyy/appearance.koplugin/commit/411e378)) — thanks to [@winstonma](https://github.com/winstonma) ([PR #126](https://github.com/Euphoriyy/appearance.koplugin/pull/126))
* **updater:** prevent manual update checks from installing an older release's ZIP under the newest version number ([a2f3b04](https://github.com/Euphoriyy/appearance.koplugin/commit/a2f3b04)) — thanks to [@winstonma](https://github.com/winstonma) ([PR #127](https://github.com/Euphoriyy/appearance.koplugin/pull/127))
* **themes:** target the selected theme when names collide ([6214d3c](https://github.com/Euphoriyy/appearance.koplugin/commit/6214d3c))
* **misc:** detect system theme on desktop by default ([852d9cf](https://github.com/Euphoriyy/appearance.koplugin/commit/852d9cf))
* **ui/background_color:** make footer color change by default ([d358832](https://github.com/Euphoriyy/appearance.koplugin/commit/d358832))
* **ui/background_color:** use inverted background as fallback accent color for progress widgets ([af0073c](https://github.com/Euphoriyy/appearance.koplugin/commit/af0073c))
* **misc:** include misc module in plugin archive ([f2ad7d2](https://github.com/Euphoriyy/appearance.koplugin/commit/f2ad7d2)) — thanks to [@winstonma](https://github.com/winstonma) ([PR #118](https://github.com/Euphoriyy/appearance.koplugin/pull/118))
* **misc:** correctly forward target night mode and detect actual state changes in night mode hooks ([3ae6472](https://github.com/Euphoriyy/appearance.koplugin/commit/3ae6472)) — thanks to [@winstonma](https://github.com/winstonma) ([PR #117](https://github.com/Euphoriyy/appearance.koplugin/pull/117))

## Performance Improvements

* **ui/background_color:** cache the tint mask for transparent icons ([ab73f99](https://github.com/Euphoriyy/appearance.koplugin/commit/ab73f99))

## Style Improvements

* **misc:** rename setting to "Follow system theme" ([70b2587](https://github.com/Euphoriyy/appearance.koplugin/commit/70b2587))
* **ui:** move font options into a dedicated fonts menu ([df0ef6f](https://github.com/Euphoriyy/appearance.koplugin/commit/df0ef6f))
* **misc:** hide unsupported menu options instead of disabling them ([19346ee](https://github.com/Euphoriyy/appearance.koplugin/commit/19346ee))

## Refactoring

* **misc:** simplify submenu iteration ([b9bc918](https://github.com/Euphoriyy/appearance.koplugin/commit/b9bc918)) — thanks to [@winstonma](https://github.com/winstonma) ([PR #119](https://github.com/Euphoriyy/appearance.koplugin/pull/119))

*Supported KOReader Version: **v2026.07***

# v1.9.0 · 2026-10-12

## [1.9.0](https://github.com/Euphoriyy/appearance.koplugin/compare/v1.8.2...v1.9.0) (2026-10-12)
[![Github Downloads (by release)](https://img.shields.io/github/downloads/Euphoriyy/appearance.koplugin/v1.9.0/total.svg)](#)

> [!IMPORTANT]  
> Sorry! The previous version of this update didn't work, if you already updated and it didn't work, please reinstall manually!


### Features

* **widgets/colorwheelwidget:** improve design and add text input ([de5d3ac](https://github.com/Euphoriyy/appearance.koplugin/commit/de5d3ac)) (SUPERSEDED)
* **widgets/colorwheelwidget:** flashing refresh on brightness changes ([367daae](https://github.com/Euphoriyy/appearance.koplugin/commit/367daae))
* add nerd font icons to menu options ([1e1f877](https://github.com/Euphoriyy/appearance.koplugin/commit/1e1f877))
* separate menus for about and updates ([94b0f66](https://github.com/Euphoriyy/appearance.koplugin/commit/94b0f66))
* **lib/updater:** prompt to turn on Wi-Fi on checking for updates ([31162aa](https://github.com/Euphoriyy/appearance.koplugin/commit/31162aa))
* **fonts:** use radio buttons for font selection ([7263abb](https://github.com/Euphoriyy/appearance.koplugin/commit/7263abb))
* **ui:** add accent color option ([72f9d6b](https://github.com/Euphoriyy/appearance.koplugin/commit/72f9d6b))
* **ui/borders:** add border thickness options ([3447109](https://github.com/Euphoriyy/appearance.koplugin/commit/3447109))
* **widgets/colorwheelwidget:** replace plus/minus buttons with brightness slider ([88240e9](https://github.com/Euphoriyy/appearance.koplugin/commit/88240e9))
* **colorwheel:** replace brightness buttons with a draggable slider ([a924645](https://github.com/Euphoriyy/appearance.koplugin/commit/a924645))


### Bug Fixes

* **book/link_color:** refresh fixed-layout docs on change ([b932924](https://github.com/Euphoriyy/appearance.koplugin/commit/b932924))
* **widgets/colorwheelwidget:** correct brightness and round corners ([07bd3c2](https://github.com/Euphoriyy/appearance.koplugin/commit/07bd3c2))
* **themes:** add empty callbacks to section headers in menus ([d2999e6](https://github.com/Euphoriyy/appearance.koplugin/commit/d2999e6))
* **ui/background_color:** retain background when a colored button is focused ([f7ef149](https://github.com/Euphoriyy/appearance.koplugin/commit/f7ef149))
* **book:** only recompute colors on setting night mode if a doc is open ([b4b130e](https://github.com/Euphoriyy/appearance.koplugin/commit/b4b130e))
* **book:** redraw page if any of the fixed page colors are applied ([c6f6861](https://github.com/Euphoriyy/appearance.koplugin/commit/c6f6861))
* fallback to default yellow link color in night mode ([b76aad4](https://github.com/Euphoriyy/appearance.koplugin/commit/b76aad4))
* **ui:** apply accent color to buttonprogresswidget ([215042d](https://github.com/Euphoriyy/appearance.koplugin/commit/215042d))
* **book/background_color:** correct night mode recoloring on e-ink ([413c081](https://github.com/Euphoriyy/appearance.koplugin/commit/413c081))
* **ui/transparency:** disable reader footer transparency by default ([dbfc8f1](https://github.com/Euphoriyy/appearance.koplugin/commit/dbfc8f1))
* **colorwheel:** reduce e-ink ghosting while dragging the wheel ([8a99efc](https://github.com/Euphoriyy/appearance.koplugin/commit/8a99efc))
* **widgets/colorwheelwidget:** update brightness gradient on pan release ([c150237](https://github.com/Euphoriyy/appearance.koplugin/commit/c150237))
* **widgets/colorwheelwidget:** update preview swatch during color selection ([b3b2f05](https://github.com/Euphoriyy/appearance.koplugin/commit/b3b2f05))
* **widgets/colorwheelwidget:** defer label update until gesture release ([0d7219d](https://github.com/Euphoriyy/appearance.koplugin/commit/0d7219d))
* **widgets/colorwheelwidget:** clear brightness slider ghosting on release ([b7ee6ca](https://github.com/Euphoriyy/appearance.koplugin/commit/b7ee6ca))
* **widgets/colorwheelwidget:** use RGB border for brightness slider ([c7ca728](https://github.com/Euphoriyy/appearance.koplugin/commit/c7ca728))
* **ui:** hook initLayer for compat w/ tapless and ligature swipes ([12af250](https://github.com/Euphoriyy/appearance.koplugin/commit/12af250))


### Performance Improvements

* reduce color wheel update costs ([0b1979e](https://github.com/Euphoriyy/appearance.koplugin/commit/0b1979e))
* **ui/font_face:** apply UI font by updating widget faces ([d183ebf](https://github.com/Euphoriyy/appearance.koplugin/commit/d183ebf))


### Style Improvements

* **widgets/colorwheelwidget:** use thicker plus/minus symbols ([3a6de68](https://github.com/Euphoriyy/appearance.koplugin/commit/3a6de68)) (SUPERSEDED)
* add separators between UI and book options ([30ddab3](https://github.com/Euphoriyy/appearance.koplugin/commit/30ddab3))
* **ui:** add separator before and after background image option ([a42a4b2](https://github.com/Euphoriyy/appearance.koplugin/commit/a42a4b2))
* **widgets/colorwheelwidget:** round apply and cancel buttons ([693b9ac](https://github.com/Euphoriyy/appearance.koplugin/commit/693b9ac))
* **ui/dict_font_face:** change icon to book ([e526127](https://github.com/Euphoriyy/appearance.koplugin/commit/e526127))
* **ui/background_image:** reorganize menu options ([b6271db](https://github.com/Euphoriyy/appearance.koplugin/commit/b6271db))
* add extra link icons and replace themes link icon ([3017e30](https://github.com/Euphoriyy/appearance.koplugin/commit/3017e30))
* switch to nerd font icons for theme and highlight color edit menus ([2ddd096](https://github.com/Euphoriyy/appearance.koplugin/commit/2ddd096))
* **themes:** add colons after option headers for current themes ([493c0b8](https://github.com/Euphoriyy/appearance.koplugin/commit/493c0b8))
* **themes:** add nerd font icons to reset themes menu ([226ae37](https://github.com/Euphoriyy/appearance.koplugin/commit/226ae37))

*Supported KOReader Version: **v2026.07***

# v1.8.2 · 2026-09-21

## [1.8.2](https://github.com/Euphoriyy/appearance.koplugin/compare/v1.8.1...v1.8.2) (2026-09-21)
[![Github Downloads (by release)](https://img.shields.io/github/downloads/Euphoriyy/appearance.koplugin/v1.8.2/total.svg)](#)


### Bug Fixes

* fix colorwheel rendering offset by @winstonma in https://github.com/Euphoriyy/appearance.koplugin/pull/105

*Supported KOReader Version: **v2026.07***

# v1.8.1 · 2026-09-21

## [1.8.1](https://github.com/Euphoriyy/appearance.koplugin/compare/v1.8.0...v1.8.1) (2026-09-21)
[![Github Downloads (by release)](https://img.shields.io/github/downloads/Euphoriyy/appearance.koplugin/v1.8.1/total.svg)](#)

> [!IMPORTANT]  
> This release resolves an issue that cause a crash when attempting to update from within the plugin. Please update manually.


### Bug Fixes

* preserve book link color on startup ([6f07ff6](https://github.com/Euphoriyy/appearance.koplugin/commit/6f07ff6a9e387e7269c19d9b32963497d713744f))
* preserve book theme colors on startup by @winstonma in #99 ([f61a0ba](https://github.com/Euphoriyy/appearance.koplugin/commit/f61a0ba78983200eb3bbc6429bc64eaeddbd0ad2))
* correct link color hex variable name ([c109d0c](https://github.com/Euphoriyy/appearance.koplugin/commit/c109d0c58e8bb83bfad71ed6e46d20ea8f3cc8fb))

*Supported KOReader Version: **v2026.07***

# v1.8.0 · 2026-09-08

## [1.8.0](https://github.com/Euphoriyy/appearance.koplugin/compare/v1.7.0...v1.8.0) (2026-09-08)
[![Github Downloads (by release)](https://img.shields.io/github/downloads/Euphoriyy/appearance.koplugin/v1.8.0/total.svg)](#)


### Features

* **book/font_color:** add dispatcher actions for toggling fixed page font color ([075f2ba](https://github.com/Euphoriyy/appearance.koplugin/commit/075f2baf0b620473a26f510b07490445bcd7ec19))
* **book/font_color:** add dispatcher actions for toggling fixed page link color ([182be74](https://github.com/Euphoriyy/appearance.koplugin/commit/182be74f9982f4cf441bef439c452f20cf62fc26))
* **book:** apply link color to fixed-layout docs ([96937ac](https://github.com/Euphoriyy/appearance.koplugin/commit/96937ac0bec17225b87d3a11282b98707c6f4e16)), closes [#94](https://github.com/Euphoriyy/appearance.koplugin/issues/94)
* **ui/misc:** add miscellaneous options for squaring corners ([94b7799](https://github.com/Euphoriyy/appearance.koplugin/commit/94b7799f82039791067e40ce2de517bf64070d7f))


### Bug Fixes

* **book/link_color:** update touchmenu items on reset ([1daf127](https://github.com/Euphoriyy/appearance.koplugin/commit/1daf1276c5c8d0a3594503f738602b19878e0e35))
* **book:** correct inversion of fixed-layout font color on Android ([1ee0793](https://github.com/Euphoriyy/appearance.koplugin/commit/1ee079375b4ee447181cf2eac88f31a6b629c3b6))
* **book:** refresh CSS on reader ready to fix inversion after restarts ([d3fd8e0](https://github.com/Euphoriyy/appearance.koplugin/commit/d3fd8e036b17e4590460f70f8a33d65ca9a0263c))
* **book:** refresh live changes to colors for fixed-layout docs ([63cf416](https://github.com/Euphoriyy/appearance.koplugin/commit/63cf41652b7c29a94d666c0e1777fd44ea2b8c88))
* **book:** remove faulty recolor skipping logic ([f98084e](https://github.com/Euphoriyy/appearance.koplugin/commit/f98084e9d145a098a2c3a6d247876882fe3818e9))
* **themes:** correct icon inversion when applying themes to "Both" ([1635526](https://github.com/Euphoriyy/appearance.koplugin/commit/16355262bc537beb6d3ce01b12ec0f05394e96aa))
* **themes:** keep menu open on resetting to current themes ([4c5ae8c](https://github.com/Euphoriyy/appearance.koplugin/commit/4c5ae8c0065a354776f9f8a5143a5baa62ec034e))
* **ui:** reload non-transparent icons on bg color changes ([843f08a](https://github.com/Euphoriyy/appearance.koplugin/commit/843f08a67ef7e310fc372f1157e83859559fc5a7))

*Supported KOReader Version: **v2026.07***
