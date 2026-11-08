# v26.11.08 · 2026-11-08

> [!WARNING]
> **BREAKING CHANGE:** `homeassistant_config.lua` now lives in `koreader/settings/` instead of the plugin folder. Your existing config is ignored until you move it there. See below.

## 1) New configuration file location

**Why:** Some Package managers replace the entire plugin folder when updating, so users lost their configuration on every update. The config now lives outside the plugin folder, so updates can no longer delete it. See: #32

**Action required when updating:**
1. **Backup your config.** Copy it from `koreader/plugins/homeassistant.koplugin/` to a safe place:
   * Coming from the last release? Back up `homeassistant_config.lua`.
   * Coming from an older release? Back up `config.lua` and rename it to `homeassistant_config.lua`.
2. Replace the contents of the `homeassistant.koplugin` folder with the files from this release.
3. Copy your backed-up `homeassistant_config.lua` into `koreader/settings/`. If a file with that name already exists there, replace it (the plugin creates a placeholder on first start).
4. Restart KOReader.

**Your folders should look like this afterwards:**

```text
koreader/
└── plugins/
    └── homeassistant.koplugin/
        ├── _meta.lua
        ├── main.lua
        ├── homeassistant_api.lua
        └── homeassistant_config.sample.lua
```

```text
koreader/
└── settings/
    ├── homeassistant_config.lua
    └── ... (other files)
```

## 2) New feature: ButtonDialog gesture

There is a new gesture action called `☰ Home Assistant: all entities`. It opens a dialog that lists every entity from your config, like a Quick Menu that is already set up for you. Unlike a manual Quick Menu, it updates itself: changes to `homeassistant_config.lua` appear after the next KOReader restart.

As with every action in this plugin, you can assign it to a KOReader gesture or use it from other plugins that support gestures, such as ZenUI.

<p align="center">
    <img src="assets/homeassistant_koplugin_buttondialog.gif" width="50%" />
</p>

<p align="center">
    <img src="https://github.com/user-attachments/assets/ceacc733-93d2-4996-8ce5-c13e4fa1b520" width="50%" />
</p>

# v26.10.19 · 2026-10-19

> [!WARNING]
> **BREAKING CHANGE:** `config.lua` is now `homeassistant_config.lua` and `api.lua` is now `homeassistant_api.lua`. Your existing `config.lua` is no longer loaded until you rename it manually, and the plugin needs the new `homeassistant_api.lua` file to start. See below.

**Action required when updating:**
1. Copy the new plugin files into the `homeassistant.koplugin` folder on your device, including the new `homeassistant_api.lua`.
2. Delete the old `api.lua` from that folder.
3. Rename your `config.lua` to `homeassistant_config.lua`. The contents stay the same.
4. Restart KOReader.

**Your folder should look like this afterwards:**

```text
📂 homeassistant.koplugin/
├── 📄 _meta.lua
├── 📄 main.lua
├── 📄 homeassistant_api.lua
├── 📄 homeassistant_config.lua   (your renamed config)
└── 📄 example_config.lua         (optional)
```

**Why:** KOReader plugins share Lua's global module cache, and `require` caches each module by name. So if two plugins both use a file called `config.lua` or `api.lua`, whichever is required first "wins", and the other plugin gets the wrong module, which can break it. Unique names like `homeassistant_config` and `homeassistant_api` avoid this.

## What's Changed
* Tidy api.lua and main.lua: group related code, clean up comments by @moritz-john in https://github.com/moritz-john/homeassistant.koplugin/pull/30
* Rename config.lua and api.lua to avoid module name clashes by @moritz-john in https://github.com/moritz-john/homeassistant.koplugin/pull/31

- Revert "Delay the re-run after Wi-Fi connects by 0.5s" (the root cause on my Kindle was buggy Amazon firmware, a firmware update + re-jailbreaking fixed the problem)


**Full Changelog**: https://github.com/moritz-john/homeassistant.koplugin/compare/v26.10.10...v26.10.19

# v26.10.10 · 2026-10-10

## What's Changed
* Merge: improve_code_quality by @moritz-john in https://github.com/moritz-john/homeassistant.koplugin/pull/28
* Delay willRerunWhenOnline callback by 0.5s by @moritz-john in https://github.com/moritz-john/homeassistant.koplugin/pull/29

**If you previously used debug_config.lua - this file must be renamed to config.lua**

From the previous release:
1) Thanks to @mehalter, the plugin now enables Wi-Fi when performing an action and then _tries_ to rerun it once Wi-Fi is on. Works well with KOReader's "Settings > Network > Action when Wi-Fi off: turn on".
2) The plugin now ships `example_config.lua` instead of `config.lua`, so updating no longer overwrites your personalized `config.lua`. **This doesn't affect existing users.** If no `config.lua` exists, a "Getting Started" menu entry explains what to do.

**New this release:**

- Delay the re-run after Wi-Fi connects by 0.5s, since the device may not be online yet and the re-run would be skipped (seen on KindleBasic5)

Small bug fixes:
```
- Give entities without a label a visible placeholder to prevent the menu and dispatcher from crashing
- Switch from (has_error, response_data) to (result, err)
- Default missing host/token to "" and make port optional, so config  problems surface as request errors instead of crashes
- Validate that action is in domain.service format and return a error otherwise
- Use socketutil timeouts and table_sink instead of the global http.TIMEOUT
- Use rapidjson.decode's own (decoded, err) return instead of pcall
- Document statesAsTemplate with an example entity and output
```

**Full Changelog**: https://github.com/moritz-john/homeassistant.koplugin/compare/v26.10.03...v26.10.10

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
