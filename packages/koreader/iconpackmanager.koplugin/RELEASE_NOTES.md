# v1.3.1 · 2026-11-11

## v1.3.1 — 修复 SVG/PNG 同名共存冲突与补充图标映射

### 🐛 问题修复
- **修复图标包内 `.svg` 与 `.png` 同名并存时误报重复图标的问题**：部分图标包会在同一目录同时提供矢量 `.svg` 与位图 `.png`（如 `align.auto.svg` + `align.auto.png`）。v1.3.0 引入 `.png` 支持后会将二者判为冲突；本版本调整优先级规则，同优先级下自动优先采用 `.svg`（同一格式重复放置仍会正常拦截报错）。

### ✨ 兼容增强
- **新增 `favorites.svg` 与 `last_document.svg` 映射**：
  - `favorites.svg` 优先映射至 Simple UI 收藏动作（`sui_action_favorites`，优先级高于 `star.empty.svg` 兜底）。
  - `last_document.svg` 在图标包缺少 `continue.svg` / `recent.svg` 时自动作为 `sui_action_continue` 与 `sui_action_recent` 的回退映射。

### 📦 安装 / 更新
下载压缩包并解压后，将 `iconpackmanager.koplugin` 文件夹覆盖放入 KOReader 的 `plugins/` 目录（例如 Android 为 `/sdcard/koreader/plugins/iconpackmanager.koplugin`），重启 KOReader 即可使用。

**Full Changelog**: https://github.com/THE-XSX/iconpackmanager.koplugin/compare/v1.3.0...v1.3.1

# v1.3.0 · 2026-11-11

## v1.3.0 — 适配新版 Simple UI 图标机制

### 🐛 问题修复
- **修复新版 Simple UI 下部分图标不生效的问题**：新版 Simple UI 已将默认图标切换为 Nerd Font 字形并由 `sui_settings.lua` 统一接管（不再读取 `simpleui.koplugin/icons/*.svg` 中的大部分文件）。本版本在检测到新版 Simple UI（存在 `infra/sui_store.lua`）时，会自动将替换后的图标同步写入 `<settings_dir>/simpleui/sui_settings.lua`，涵盖 **49 个 Simple UI 图标槽位**（29 个 `simpleui_sysicon_*` 系统槽位 + 20 个 `simpleui_action_*_icon` 快捷动作槽位）。
- **修复重启时配置可能被旧缓存覆盖的问题**：若 Simple UI 已在内存中加载，更换或恢复图标时会同步更新并刷新其运行时的 `infra/sui_store` 缓存，确保重启后配置稳定生效。
- **修复恢复默认图标与旧版升级残留**：应用新包或点击“恢复官方默认图标”时，会清理插件写入的 Simple UI 槽位配置及 `<data_dir>/icons/simpleui_sui_tab_*` 残留文件，并自动还原 v1.2.0 时期在 `simpleui.koplugin/icons/` 中修改过的文件。
- **修正 `simpleui/` 路径识别与相对配置路径**：支持直接识别图标包内的 `simpleui/` 子目录，同时避免将根封装文件夹名为 `simpleui/` 的纯 KOReader ZIP 包误判；当 `settings_dir` 为 `./settings` 且数据目录为绝对路径时自动规范化为绝对路径。

### ✨ 新增与改进
- **三套命名兼容与优先级合并**：
  1. 新版 Simple UI 命名（`sui_menu.svg`、`sui_action_library.svg`、`sui_tab_main.svg` 等）
  2. 旧版 Simple UI 命名（`library.svg`、`more-options.svg`、`back.svg` 等）
  3. KOReader `mdlight` 自动回退映射（如 `appbar.menu.svg`、`chevron.*.svg`、`back.top.svg`、`exit.svg`、`home.svg` 等会同步映射至 Simple UI 对应标题栏、分页箭头、收藏夹返回、退出按钮、Tab 栏与快捷动作）
- **新增 `.png` 图标支持**：除 `.svg` 外，现在也支持 `.png` 格式图标并保留原始扩展名；完整性检测报告文案同步调整。
- **内置官方图标同步**：更新至 `koreader/koreader@eaa6a09`（102 个 `mdlight` 图标）与 `doctorhetfield-cmd/simpleui.koplugin@4c0a388`（18 个图标），移除上游已废弃的 `back.svg`、`default.svg`、`more-options.svg`。
- **兼容旧版与纯 KOReader**：未安装 Simple UI 或仍在使用旧版 Simple UI（无 `infra/sui_store.lua`）的设备继续保持原有行为。

### 📦 安装 / 更新
下载压缩包并解压后，将 `iconpackmanager.koplugin` 文件夹覆盖放入 KOReader 的 `plugins/` 目录（例如 Android 为 `/sdcard/koreader/plugins/iconpackmanager.koplugin`），重启 KOReader 即可使用。

**Full Changelog**: https://github.com/THE-XSX/iconpackmanager.koplugin/compare/v1.2.0...v1.3.0

# v1.2.0 · 2026-10-24

### 🌟 新特性与重大改进

1. **安卓全平台原生适配（免改程序本体）**
   - 采用 KOReader 官方推荐的用户图标覆盖机制（`<数据目录>/icons`，安卓上对应 `/sdcard/koreader/icons`）。
   - 彻底解决 Android 设备上因程序目录在应用私有存储中导致的无法写入或只读权限问题。
   - **KOReader OTA 升级不丢图标**：今后在线升级或覆盖安装 KOReader APK，均不会重置用户数据目录，主题持久保留。

2. **内置官方图标包，免去首次强制备份**
   - 插件直接内置了 KOReader 官方最新 102 个 `mdlight` SVG 图标与 Simple UI 官方 21 个 SVG 图标。
   - **开箱即用**：无需像旧版一样必须先执行“备份原版图标”，扫描后直接“一键更换”。
   - 随时可点击“**恢复官方默认图标**”进行秒级无损复原。

3. **双向兼容 Simple UI 智能探测**
   - 自动适配 Simple UI 安装在安卓存储（`/sdcard/koreader/plugins/simpleui.koplugin`）或程序内目录的不同路径。
   - 无论是否安装 Simple UI，都能平滑降级或协同替换。

4. **旧版本自动无损平滑迁移**
   - 针对从 v1.1 及更早版本升级的用户，插件启动时会自动检测是否存在旧备份；若存在，会自动将原版资源还原写回 KOReader 程序目录，并自动清理废弃的 `original/` 备份文件夹。

---

### 📦 安装方法

1. 下载附件中的 `iconpackmanager.koplugin-v1.2.0.zip` 并解压。
2. 将解压得到的 `iconpackmanager.koplugin` 文件夹复制到设备的 `plugins/` 目录：
   - **Android**: `/sdcard/koreader/plugins/iconpackmanager.koplugin`
   - **Kindle**: `/koreader/plugins/iconpackmanager.koplugin`
   - **Kobo**: `/.adds/koreader/plugins/iconpackmanager.koplugin`
3. 重启 KOReader 即可在顶部菜单“**工具 -> 图标包管理器**”中看到。

---

### 💡 从旧版本升级注意事项

1. **重新应用一次图标包**：
   如果升级前已在使用第三方图标包，建议升级插件后打开“扫描到的图标包”，重新点击一次该主题的“一键更换”，将图标规范部署至新的覆盖目录。
2. **图标包存放目录**：
   建议在存储中新建目录（如 `/sdcard/koreader/iconpacks/`）存放下载的主题，请勿将图标包解压到系统保留的 `/sdcard/koreader/icons` 目录中。

# v1.1.0 · 2026-08-19

# KOReader 图标包管理器 (Icon Pack Manager) v1.1.0
专为 KOReader 打造的图标主题管理切换插件。支持 KOReader 原生浅色图标（`mdlight`）以及 Simple UI 图标的双向兼容管理，提供受保护的原版备份与异常自动回滚机制，让图标美化更简单、更安全！
---

## 核心特性
**安全备份与原子切换**
  * 强制首选“备份原版图标”，将原版资源持久化保存在受保护的专属目录；
  * 采用临时阶段构建与原子重命名机制，若发生错误秒级自动回滚，杜绝白屏与图标丢失。
**智能双向兼容 Simple UI**
  * 自动检测当前设备是否安装了 `simpleui.koplugin` 插件；
  * 若已安装则双目录协同替换，未安装则自动降级为仅管理 KOReader 原版图标，即装即用。
**多种图标包格式支持**
  * **平铺文件夹**：直接识别图标包目录下的各子文件夹作为独立主题；
  * **嵌套多版本**：支持单主题内包含多种子风格（如深色/彩色版本）的自动识别；
  * **ZIP 压缩包**：支持标准层级或平铺 SVG 的 ZIP 压缩包，无需提前解压。
 **图标完整性检测报告**
  * 直观展示每个图标包对 KOReader 与 Simple UI 的覆盖率；
  * 详细列出缺少匹配的原版图标以及未被识别的未知 SVG。
 **随时一键恢复**
  * 随时可点击“恢复原版图标”一键回到最初的官方图标状态。
---

## 安装方法
1. 下载下方 Assets 中的 `iconpackmanager.koplugin.zip`。
2. 解压并将 `iconpackmanager.koplugin` 文件夹整体放入设备的 `koreader/plugins/` 目录。
3. 重启 KOReader 即可在顶部菜单 **“工具 -> 图标包管理器”** 中使用。
---

## 快速上手流程

1. 打开 **“工具 -> 图标包管理器”**，首先点击 **“备份原版图标”**。
2. 点击 **“图标包文件夹”**，选择你存放图标包的路径（如 `/sdcard/icons` 或 `koreader/icons`）。
3. （可选）点击 **“图标完整性检测”**，查看各图标包的覆盖与缺失详情。
4. 点击 **“扫描到的图标包”**，选中喜爱的主题并点击 **“一键更换”**。
5. 按提示重启 KOReader 即可享受全新图标界面！
---

## 注意事项

* **OTA 升级提醒**：KOReader 在线升级固件时会重置原版图标目录。若升级了 KOReader 版本，建议在插件中重新备份一次原版图标后再应用主题。
* **备份文件位置**：原版备份保存于 `settings/iconpackmanager/original/`，卸载插件前请勿误删此目录以保留还原能力。
---
