# v1.2.0 · 2026-11-20

## New Features

* **Automatic updates.** Once a day, the plugin checks GitHub for a new release. When there is one, a popup offers to install it, and the plugin's menu entry shows "(update available)". Tap "Update now" and restart KOReader when asked. You can turn this off by unchecking "Check for updates automatically".
* **Battery indicator.** The lockscreen can now show the battery level: as a bar along the bottom edge (with adjustable thickness) or as an icon and percentage in the header. It's off by default; turn it on under "Battery indicator".
* Thanks to @rogervokma-stack, WeatherLockscreen is now available in Japanese.

## Changes

* The scaling and rotation overrides are combined into a single "Overrides" entry to keep the menu compact. 
* The plugin's menu entry now shows an icon for the current weather, and the "Battery indicator" entry shows the live battery state.
* Added missing Chinese and Japanese translations. "Unknown Title" and "No book" on the Reading display are now translated in all languages.

## Notes

This is the last release you have to install by hand. From now on, new versions can be installed from within KOReader. Installing updates this way needs a recent KOReader version; on older versions, update manually as before.

## What's Changed
* Add Japanese translation by @rogervokma-stack in https://github.com/loeffner/WeatherLockscreen/pull/41
* Feature/battery indicator by @loeffner in https://github.com/loeffner/WeatherLockscreen/pull/42

## New Contributors
* @rogervokma-stack made their first contribution in https://github.com/loeffner/WeatherLockscreen/pull/41

**Full Changelog**: https://github.com/loeffner/WeatherLockscreen/compare/v1.1.0...v1.2.0

# v1.1.0 · 2026-11-01

## New Features

* Thanks to @oldman63 WeatherLockscreen plugin is now available in Hungarian.
* WeatherLockscreen will now prefer its own translations over those from KoReader.

## What's Changed
* Add Hungarian localization by @oldman63 in https://github.com/loeffner/WeatherLockscreen/pull/39
* Fix plugin translation priority and preserve KOReader fallback by @oldman63 in https://github.com/loeffner/WeatherLockscreen/pull/40

## New Contributors
* @oldman63 made their first contribution in https://github.com/loeffner/WeatherLockscreen/pull/39

**Full Changelog**: https://github.com/loeffner/WeatherLockscreen/compare/v1.0.0...v1.1.0

# v1.0.0 · 2026-09-19

## New Features

* Thanks to @lianyis  WeatherLockscreen plugin is now available in Simplified Chinese.
* Users can now select a different interval for Active Sleep while the device is charging.

## Bugs fixed
* Active Sleep now functions also while the device is charging.

## Notes
As you can see, I have decided to finally set the version to 1.0.0. I feel like the plugin is now stable and feature-rich enough that this is warranted. This does not mean, that I will stop maintaining, fixing bugs or even developing new features. 
Going forward I will use the [semantic versioning system](https://semver.org/). 

## What's Changed
* Add Simplified Chinese translation. by @lianyis in https://github.com/loeffner/WeatherLockscreen/pull/38

## New Contributors
* @lianyis made their first contribution in https://github.com/loeffner/WeatherLockscreen/pull/38

**Full Changelog**: https://github.com/loeffner/WeatherLockscreen/compare/v0.9.7-beta.1...v1.0.0

# v0.9.7-beta.1 · 2026-06-28

### This is a beta release.

<img width="1600" height="1282" alt="IMG_6390" src="https://github.com/user-attachments/assets/ca98b377-2d8c-45c6-b31a-9b34489e0900" />


It's been a while since I tinkered with my kindle. It's about time this plugin gets some love again.
The statistics show that there are still quite a few users enjoying it. (Unless someone is misusing my API key :D)
Well, here we go:

## Changes 

* Users can now select the shown hours directly in the settings: no need for the user patch anymore. 
* There is now an `Override Rotation` setting, which allows you to put the screensaver in landscape mode. 
* Adapted layouts for Today&Tomorrow, Today, Current for landscape modes. 
* Added icons to the settings menu, which hopefully make it a bit prettier and easier to read.


## Bugs fixed

* Fixed a crash in cover mode, when no cover is available for the last book


## What's Changed
* Landscape mode by @loeffner in https://github.com/loeffner/WeatherLockscreen/pull/35


**Full Changelog**: https://github.com/loeffner/WeatherLockscreen/compare/v0.9.6-beta.2...v0.9.7-beta.1

# v0.9.6-beta.2 · 2026-02-21

### This is a beta release.

## Changes 

* Menus now use radio buttons, when the user can choose a predefined set of mutually exclusive options.

## Bugs fixed

* Fixed potential crashes.
* Several refactoring to make the code easier to read.
* Removed uneccessary files from the install zip.

## What's Changed
* Bugfixes and refactorings by @loeffner in https://github.com/loeffner/WeatherLockscreen/pull/29

**Full Changelog**: https://github.com/loeffner/WeatherLockscreen/compare/v0.9.6-beta.1...v0.9.6-beta.2
