# v26.10.03 · 2026-10-03

## What's Changed
* Add network check before calling Home Assistant API by @moritz-john in https://github.com/moritz-john/homeassistant.koplugin/pull/26
* Handle missing config.lua with a Getting Started menu entry by @moritz-john in https://github.com/moritz-john/homeassistant.koplugin/pull/27

**If you previously used `debug_config.lua` - this file must be renamed to `config.lua`**

Two big changes this version:

1) Thanks to @mehalter `homeassistant.koplugin` now enables Wi-Fi when performing an action and then _tries_ to rerun the action after Wi-Fi is enabled.  
This feature works well combined with the KOReader setting: "Settings > Network > "Action when Wi-Fi off: turn on".

2) `homeassistant.koplugin` now ships with `example_config.lua` instead of `config.lua`.

	**This doesn't affect existing users.** The change ensures that updating the plugin no longer overwrites your personalized `config.lua`.

	If no `config.lua` exists, the plugin now shows a single "Getting Started" menu entry. This helps users who skipped the README or installed the plugin through something like `storefront.koplugin` without realizing they need to create their own `config.lua`.

Getting Started message:	
<img width="500" alt="2026-10-03 at 11 39 40 Screenshot@2x" src="https://github.com/user-attachments/assets/1098cc8a-e7b2-4e84-92cd-a09ee43ac3fa" />




**Full Changelog**: https://github.com/moritz-john/homeassistant.koplugin/compare/v26.03.19...v26.10.03

# v26.03.19 · 2026-03-19

- The "Heartbeat" / Home Assistant sensor feature now lives in a different plugin: https://github.com/moritz-john/heartbeat.koplugin
- This means that `koreader_sensor_name` and `sensor_resume_delay` can be deleted from your homeassistant.koplugin `config.lua` file.
- The new plugin allows you to change these values directly from within the KOReader GUI.

<img width="692" height="467" alt="heartbeat_settings" src="https://github.com/user-attachments/assets/33f13523-7ac4-4b26-b322-fa852acdbc1b" />

**Full Changelog**: https://github.com/moritz-john/homeassistant.koplugin/compare/v26.02.26...v26.03.19

# v26.02.26 · 2026-02-26

This update focuses primarily on refactoring and general code cleanup to improve maintainability 

- **State queries have been completely refactored** 
  - The plugin now performs a templating request to `/api/template`
  - States automatically include their unit of measurement (when available)
  - Binary states are now localized (e.g., "Open/Closed" instead of "on/off" for doors)
  - Date values such as `last_changed` are formatted in a more user-friendly way
- The sensor update delay after device resume is now configurable via: `sensor_resume_delay` in `config.lua`; the default is now 8 seconds[^1]
- Removed `messages.lua`; added `api.lua`
- Removed "response data" support from actions (todo.get_items & weather.get_forecasts)[^2]

<img width="474" height="198" alt="door_example" src="https://github.com/user-attachments/assets/e63492b4-7cff-4b5b-87e5-0c039798aba7" />

[^1]:A delay of 4 seconds works well on my Kindle, allowing enough time to reconnect to Wi-Fi.
Kobo devices may require a slightly longer delay.
[^2]: I spent way too much time on this niche feature (over 40 hours) and was never happy with how it turned out

**Full Changelog**: https://github.com/moritz-john/homeassistant.koplugin/compare/v26.02.03...v26.02.26

# v26.02.03 · 2026-02-03

- Fix potential crash if author value is nil (Thanks @noxhirsch for reporting)
- Re-add battery information to Home Assistant sensor

**Full Changelog**: https://github.com/moritz-john/homeassistant.koplugin/compare/v26.02.02...v26.02.03

# v26.02.02 · 2026-02-02

- Added title and author metadata to the `koreader_status` Home Assistant sensor attributes
- Removed battery information from the sensor[^1]
- Expanded sensor state updates to also trigger on document open and close
- Added error logging when sending sensor state fails
- Introduced an `isConnected()` network check for the `sendHeartbeat` feature

**Full Changelog**: https://github.com/moritz-john/homeassistant.koplugin/compare/v26.01.24...v26.02.02

[^1]: Battery information was removed because it only makes sense when the `koreader_status` sensor is updated periodically (e.g. every 5 minutes), which is not currently the case (and I don't see an use case for this feature at the moment).

<img width="1840" height="542" alt="2026-02-02 at 17 33 24 Screenshot" src="https://github.com/user-attachments/assets/e9981525-72e5-4274-a35c-f2a89bc849be" />
