# 26.11.20 · 2026-11-20

## What's New

### Font Catalog Overhaul & Live Previews
- **Leaner, dedicated font catalog:** Redesigned the font catalog architecture so font metadata and live preview typefaces are fetched from a dedicated fonts catalog and cached on demand rather than bundled in the plugin archive. View the new web catalog here and submit new fonts for consideration: https://ultimatejimmy.github.io/storefront-fonts/
- **New Display category:** Added a **Display** filter to both the plugin and the web catalog so decorative, handwritten, and thematic fonts are easier to find.
- **Download counts & sorting:** Replaced star counts on the Fonts tab and Details dialog with **download counts**, and made **Most Downloaded** the default font sort (alongside *Most Liked* and *Name*).
- **Font preview cache management:** Added **Font preview typefaces** to the Clear Cache dialog so cached preview fonts can be inspected and cleared independently.

### 35 New Open-License Fonts (56 Total)
Expanded the font catalog with 35 new open-license fonts across classic book serifs, handwritten styles, fantasy/storybook lettering, and nautical themes:
- **Classic & Book Serifs:** *EB Garamond*, *Crimson Pro*, *Vollkorn*, *Alegreya*, *Spectral*, *Gelasio*, *Ibarra Real Nova*, *Junicode*
- **Handwritten & Casual:** *Shantell Sans*, *Caveat*, *Patrick Hand*, *Comic Neue*, *Fredoka*
- **Fantasy, Storybook & Medieval:** *Fraunces*, *IM Fell English*, *Cormorant Garamond*, *Cinzel*, *Fondamento*, *MedievalSharp*, *UnifrakturMaguntia*, *Uncial Antiqua*, *Metamorphous*, *Almendra*, *Almendra Display*, *Eagle Lake*, *Macondo Swash Caps*, *Berkshire Swash*, *Basteleur*, *Avara*
- **Pirate & Nautical:** *Pirata One*, *Trade Winds*, *Grenze Gotisch*, *Jolly Lodger*, *Seaweed Script*, *The Nautigal*

### Installed Tab & UI Improvements
- **Plugin versions on Installed tab:** Installed plugins now display their version number (e.g., `v26.11.17`) on the **Installed** tab when available.
- **Faster font browsing:** Optimized font list height measurement, user font directory caching, and cache invalidation to make scrolling and installing fonts more responsive.

### Bug Fixes
- **Fixed likes not always updating:** Retired the stale local ratings cache file and reconciled session votes against catalog generation timestamps so community likes and counts stay up to date.
- **De-duplicated likes across same-named repos:** Scoped plugin and patch rating keys strictly to repository ID or `owner/repo` instead of bare repository or directory names, preventing like/download collisions between different repositories with the same name.
- **Installed plugin metadata & update fixes:** Improved catalog metadata lookup on the **Installed** tab (owner, stars, description, and likes) and preserved the active install directory when updating plugins from the Details or About dialog.



**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.9...26.11.20

# 26.11.9 · 2026-11-09

- Update delete logic 
- Load readme in the background without UI blocking
- Update version check logic to be more robust

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.11.1...26.11.9

# 26.11.1 · 2026-11-02

- fix bug with branch install feature
- Add cache limit feature/setting
- Update the logic for the "Check for updates" button

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.28...26.11.1

# 26.10.28 · 2026-10-28

Mostly back-end performance improvements and bug fixes:
- Fix bug with suspend https://github.com/ultimatejimmy/storefront.koplugin/issues/5079
- Fix https://github.com/ultimatejimmy/storefront.koplugin/issues/5080
- Fix https://github.com/ultimatejimmy/storefront.koplugin/issues/5081
- Update font https://github.com/ultimatejimmy/storefront.koplugin/issues/5082

New feature: 
- Add screensaver collections feature

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.20...26.10.28

# 26.10.20 · 2026-10-20

## What's Changed
* Fix archive root detection for plugins with embedded components by @komadorirobin in https://github.com/ultimatejimmy/storefront.koplugin/pull/5078
* Fix patch update logic https://github.com/ultimatejimmy/storefront.koplugin/issues/5076
* Fix updates with native libraries https://github.com/ultimatejimmy/storefront.koplugin/issues/5077
* Catalog logic tweak
* memory fix

## New Contributors
* @komadorirobin made their first contribution in https://github.com/ultimatejimmy/storefront.koplugin/pull/5078

**Full Changelog**: https://github.com/ultimatejimmy/storefront.koplugin/compare/26.10.16...26.10.20
