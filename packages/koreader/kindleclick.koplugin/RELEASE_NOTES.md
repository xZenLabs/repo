# v1.7.21 · 2026-11-27

# Kindle Click 蓝牙 v1.7.21 / Kindle Click Bluetooth v1.7.21

## 中文

### 本次更新

- 修复菜单复选框与实际蓝牙状态不同步的问题：分类条目不再显示勾选，开关项改为显示「开启蓝牙 / 关闭蓝牙」。
- 界面跟随 KOReader 语言：中文界面显示中文，英文界面显示英文；插件更名为「Kindle蓝牙和翻页器」（英文界面：Bluetooth and Kindle Click Controller）。
- 内置更新更稳妥：更新清单的路径会严格校验，拒绝任何越出插件目录的条目，并限制条目数量与单个文件大小。
- 修复从旧版本升级时无法创建 `l10n/` 子目录、导致内置更新失败的问题。

### 升级

1. 退出 KOReader，覆盖 `plugins/kindleclick.koplugin` 文件夹（或在菜单里使用「检查更新」）；
2. 重启 KOReader。

---

## English

### Changes

- Fixed the menu checkbox getting out of sync with the real Bluetooth state: the category entry no longer shows a tick, and the switch item now reads "Turn Bluetooth on / Turn Bluetooth off".
- The UI now follows KOReader's language: Chinese in a Chinese UI, English otherwise. The plugin is now named "Bluetooth and Kindle Click Controller" (Chinese UI: Kindle蓝牙和翻页器).
- Hardened the built-in updater: manifest paths are validated and anything escaping the plugin directory is rejected, with limits on entry count and file size.
- Fixed in-app updates failing from older versions because the `l10n/` subdirectory could not be created.

### Upgrade

1. Exit KOReader and replace the `plugins/kindleclick.koplugin` folder (or use "Check for updates" in the menu);
2. restart KOReader.

# v1.7.19 · 2026-11-21

Bluetooth and Kindle Click controller for KOReader v1.7.19 / KOReader蓝牙和翻页器控制插件 v1.7.19

English
Changes
the frozen Bluetooth stack rescue: when the native stack wedges after a long sleep, one tap rebuilds the transport and restores the Click in about 40 seconds.
Upgrade
Exit KOReader and replace the plugins/kindleclick.koplugin folder;
restart KOReader.

中文
本次更新
「系统蓝牙假死救回」：长时间休眠后原生蓝牙假死时，可一键重建蓝牙传输层，约 40 秒恢复连接。
升级
退出 KOReader，覆盖 plugins/kindleclick.koplugin 文件夹；
重启 KOReader。

# v1.7.18 · 2026-11-15

# Kindle Click 蓝牙 v1.7.18 / Kindle Click Bluetooth v1.7.18

## 中文

### 本次更新

- 新增 ZenOS 主屏「Kindle Click」小组件：显示蓝牙关闭 / 翻页器断开 / 翻页器连通三种状态，点击组件会打开快捷菜单（开关蓝牙、连接、重建传输层、检查更新、诊断）。组件默认关闭，到 **Zen Settings → Home → Widgets** 打开即可；未安装 ZenOS 时自动跳过。
- ZenOS Controls 的按钮图标：插件启动时把 `kindleclick.svg` 复制到 KOReader 的 `icons/`，在按钮图标选择器里选 `kindleclick` 即可。ZenOS 的已激活黑底只作用于内置按钮，自定义按钮无法随 Click 状态变黑底，按钮文字也不能动态变化。
- 连接成功提示：点「连接 Kindle Click」或唤醒后自动重连成功时，会弹出「Kindle Click 已连接」。
- 检查更新修复：不再使用会抛异常的 Turbo HTTP 客户端，改为 LuaSocket 直连；下载源改为 5 个 jsDelivr 镜像 + 3 个 raw 镜像依次回退，失败时日志会记录每个镜像的具体错误，不再只显示 `request_failed`。
- 1.7.16 的「检查更新（带版本号）」、菜单回到 **设置 → 网络**、传输层重建与休眠期不读状态等改动保持不变。

### 升级

1. 退出 KOReader，覆盖 `plugins/kindleclick.koplugin` 文件夹；
2. 重启 KOReader。

---

## English

### Changes

- Adds a **Kindle Click** Home widget for ZenOS that shows one of three states: Bluetooth off, page turner disconnected, or page turner connected. Tapping it opens a quick menu (toggle Bluetooth, connect, rebuild the transport, check for updates, diagnostics). It starts disabled; enable it under **Zen Settings → Home → Widgets**. Plugins without ZenOS skip the registration automatically.
- ZenOS Controls button icon: at startup the plugin copies `kindleclick.svg` into KOReader's `icons/`, so `kindleclick` is directly selectable in the button icon picker. ZenOS's active-state dark background only applies to its built-in buttons; custom buttons cannot turn dark when the Click connects, and their label cannot change dynamically.
- A "Kindle Click connected" message now appears after a manual connect or a successful automatic reconnect after wake.
- Update check fixed: it no longer uses the Turbo HTTP client that threw on some Kindle builds and now connects through LuaSocket; downloads fall back across five jsDelivr mirrors plus three raw mirrors, logging the concrete error per mirror instead of just `request_failed`.
- Everything from 1.7.16 is unchanged: the manual **Check for updates** entry with the current version, the menu under **Settings → Network**, the transport rebuild, and no Bluetooth reads while suspended.

### Upgrade

1. Exit KOReader and replace the `plugins/kindleclick.koplugin` folder;
2. restart KOReader.

# v1.7.17 · 2026-11-15

# Kindle Click 蓝牙 v1.7.17 / Kindle Click Bluetooth v1.7.17

## 中文

### 本次更新

- 新增 ZenOS 主屏「Kindle Click」小组件：显示蓝牙关闭 / 蓝牙已开启 / 翻页器已连接三种状态，点击组件会打开快捷菜单（开关蓝牙、连接、重建传输层、检查更新、诊断）。组件默认关闭，到 **Zen Settings → Home → Widgets** 打开即可；未安装 ZenOS 时自动跳过。
- 1.7.16 的「检查更新（带版本号）」、菜单回到 **设置 → 网络**、传输层重建与休眠期不读状态等改动保持不变。

### 升级

1. 退出 KOReader，覆盖 `plugins/kindleclick.koplugin` 文件夹；
2. 重启 KOReader。

---

## English

### Changes

- Adds a **Kindle Click** Home widget for ZenOS that shows one of three states: Bluetooth off, Bluetooth on, or page turner connected. Tapping it opens a quick menu (toggle Bluetooth, connect, rebuild the transport, check for updates, diagnostics). It starts disabled; enable it under **Zen Settings → Home → Widgets**. Plugins without ZenOS skip the registration automatically.
- Everything from 1.7.16 is unchanged: the manual **Check for updates** entry with the current version, the menu under **Settings → Network**, the transport rebuild, and no Bluetooth reads while suspended.

### Upgrade

1. Exit KOReader and replace the `plugins/kindleclick.koplugin` folder;
2. restart KOReader.

# v1.7.16 · 2026-11-15

# Kindle Click 蓝牙 v1.7.16 / Kindle Click Bluetooth v1.7.16

## 中文

### 本次更新

- 新增手动「检查更新（带当前版本号）」：联网后点击检查，发现新版本可下载替换，重启 KOReader 生效。
- 菜单入口回到 **设置 → 网络 → Kindle Click**，并移除「使用说明」菜单项。
- 「重建蓝牙传输层（实验）」在多次真实断联中验证可用，约 40 秒恢复蓝牙并自动重连 Click。
- 修正重建日志把 `start/running`、`stop/waiting` 误报为失败的问题。
- 休眠期间不再读取蓝牙状态，避免挂起/唤醒过渡中的多余 LIPC 调用。

### 升级

1. 退出 KOReader，覆盖 `plugins/kindleclick.koplugin` 文件夹；
2. 重启 KOReader。

---

## English

### Changes

- Adds a manual **Check for updates** entry that shows the current version: tap it while online, and a new version can be downloaded and installed; restart KOReader afterwards.
- The menu entry is back under **Settings → Network → Kindle Click**, and the **Usage notes** item has been removed.
- **Rebuild Bluetooth transport (experimental)** is now verified across repeated real disconnects: it restores Bluetooth in about 40 seconds and reconnects the Click automatically.
- Rebuild logging no longer reports `start/running` / `stop/waiting` as failures.
- Bluetooth status is no longer read while the device is suspended, avoiding extra LIPC calls around suspend and resume.

### Upgrade

1. Exit KOReader and replace the `plugins/kindleclick.koplugin` folder;
2. restart KOReader.
