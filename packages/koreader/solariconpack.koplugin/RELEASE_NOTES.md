# v1.2.0 · 2026-11-04

Solar now has icons for ZenOS and Project: Title, in both Colour and Mono. When you install, Solar sets up KOReader and the icons for the UI you're using: SimpleUI, ZenOS or Project: Title.

- **ZenOS:** a full icon pack covering ZenOS, PM and FM. Supplementary icons are added as extra choices for App Launcher shortcuts.
- **Project: Title:** title bar icons, and its book and folder images.
- **SimpleUI:** an icon for the new Exit Book button, so the pack covers all 48 SimpleUI icons.
- **Supplementary icons:** up from 84 to 173, with simple names that describe each drawing.
- **Change to plugin structure:** each drawing is now stored once, and the plugin builds the pack it needs when you install.

<details>
<summary>New icons (72)</summary>

`ao3`, `atom`, `battery_charging`, `battery_half`, `battery_low`, `bell`, `bell_off`, `blocks`, `book`, `bookorbit`, `bug`, `candle`, `chart_up`, `checklist`, `clapperboard`, `clipboard`, `compass`, `connections`, `cpu`, `database`, `debug`, `downgrade`, `downloads`, `education`, `enable`, `extend`, `filter`, `font`, `forge`, `gestures`, `grid`, `incognito`, `keyboard`, `koreader`, `lightning`, `mail`, `media`, `more_vertical`, `network`, `open_box`, `open_link`, `origami`, `package`, `patches`, `pause`, `pie_chart`, `qrcode`, `queue_remove`, `remove`, `scan`, `scan_plugins`, `shield_check`, `shield_lock`, `shield_warning`, `skip_left`, `skip_right`, `sliders_horizontal`, `snowflake`, `sort`, `sort_asc`, `sort_desc`, `speed`, `spinning_top`, `theme`, `toc`, `unverified`, `update`, `upgrade`, `upload`, `verified`, `wallpaper`, `waveform`

</details>

### Notes
- **Manual installs** now cover the KOReader icons only. The SimpleUI, ZenOS and Project: Title icons need the plugin.
- **Renamed icons:** some pre-existing supplementary icons have been renamed, and you may need to reapply following this update.
- **Known issues:** A few places in ZenOS load its own icons directly instead of through icon packs, so they keep ZenOS's icons even with Solar selected. This has been reported to ZenOS, and Solar already includes the icons for when it's fixed.

Updating: Choose **Check for updates** in **Tools → Solar Icon Pack**. After KOReader restarts, choose your style again to install the new icons. For more information see the [README](https://github.com/pxlflux/solariconpack.koplugin#readme).

# v1.1.0 · 2026-10-18

60 new supplementary icons

* **New icons:** the supplementary set grows from 24 to 84 icons, in both Colour and Mono. The new icons are: 
airplane_mode, anki, annas_archive, appearance, archive, audiobook, bin, bluetooth, bookends, bookends_alt, bookshelf_alt, brightness, browser, calculator, calibre, chess, continue_alt, customisable_sleep_screen, device, dictionary, downloads, folder_open, gallery, games, glimpse, good_reads, hardcover, highlight, home_assistant, ink_away, launcher, lock, news, notion, obsidian, opds, pencil, quit, rakuyomi_alt, readeck, readest, reading_insights, restart, rss, share, storygraph, sync, terminal, timer, toggle, translate, volume, wallabag, warmth, weather, weread, wikipedia, word_search, x_ray, zotero
* **New designs:** `instapaper` and `zlibrary` have new designs. The filenames haven't changed, so any Quick Actions already using them update automatically.
* **SimpleUI pack update:** now covers the `Search` quick action added in SimpleUI 2.7.5, using Solar's search icon. That makes 47 slots in total.

**Updating:** if you installed with the plugin, go to `Tools → Solar Icon Pack → Check for updates`, then choose `Reinstall` after restarting to get the new icons. For manual installation, see the [README](https://github.com/pxlflux/solariconpack.koplugin#readme).

# v1.0.0 · 2026-10-02

Initial release.

- 102 KOReader icons, 34 SimpleUI pack icons (covering all 46 slots) and 24 supplementary icons.
- Colour and Mono versions.
- Copy the plugin to `koreader/plugins/`, then choose a style in **Tools → Solar Icon Pack**, or copy the icons manually (see the [README](https://github.com/pxlflux/solariconpack.koplugin#readme)).

Download `solariconpack.koplugin.zip` below.
