# v3.4.0 · 2026-11-25

# 文笺 (Type Folio) v3.4.0

本次更新重点围绕 **EPUB 对话版图书的批量处理、规范命名导出与安全原地覆盖** 展开，同时引入包内指纹标记，让导出或重命名后的对话版 EPUB 在任何目录下都能零延迟识别并直接应用对话排版。

---

## ✨ 新增功能

### 1. 文件管理器 & 阅读器双入口批量处理
- **文件管理器独立入口**：插件放开 `is_doc_only` 限制（[main.lua](file:///d:/code/typefolio.koplugin/main.lua#L350-L353)），无需打开书籍即可在 KOReader 文件管理器的 **工具菜单** 中打开 **「文笺：批量处理对话图书」**，同时支持直接在其中清理缓存的 `.tf_dlg.epub` 对话副本。
- **阅读器内快捷入口**：在 **「正文与章节 → 对话」** 菜单中新增：
  - **导出规范命名副本到文件夹…**
  - **覆盖当前书为对话版（自动备份）…**
  - **批量处理文件夹内的图书…**

### 2. 两种输出模式：规范导出 & 安全原地覆盖
- **保存到指定文件夹（导出模式）**：
  - 自动解析 EPUB 内部 `META-INF/container.xml` → `.opf` 的 `<dc:title>` 与 `<dc:creator>` 元数据，清洗非法文件名字符后按 **`书名-作者-文笺.epub`** 或 **`书名-作者.epub`** 规范命名导出（「文件名附加『-文笺』后缀」可自由开关）。
  - 支持 **包含子文件夹** 递归扫描与 **导出时保留子文件夹层级**，并自动将原书阅读进度与 `99_typefolio.css` 样式微调启用状态同步到导出副本（[.sdr](file:///d:/code/typefolio.koplugin/tools/epub_batch.lua#L261-L294)）。
- **覆盖原书（可自动备份）**：
  - 始终先生成临时工作文件 `.tf_work.epub` 并完整校验成功后再替换原书，避免中途出错损坏原文件。
  - 默认开启 **覆盖前备份原书**（自动备份至 `.typefolio_backup/`，支持自定义备份目录或关闭备份）。
  - 默认开启 **覆盖时保留原文件名**，完整保留 KOReader 原有 `.sdr` 阅读进度、划线笔记与合集记录；若关闭保留原文件名并按规范改名，也会自动迁移 `.sdr` 并清理旧路径 sidecar。

### 3. 墨水屏友好的异步分步批处理队列
- 通过 `UIManager:scheduleIn` 按本分步让出事件循环，保证墨水屏设备在批量加工期间界面可响应，实时显示 `处理进度 (X / Y)` 并支持中途 **取消**（当前书完成后安全停止）。
- 默认开启 **跳过已标注或已存在的图书**（同时自动跳过当前正在阅读的书籍、`.` 开头隐藏目录、`.sdr`、缓存目录及目标/备份目录）。
- 批处理完成后自动刷新文件管理器目录，并弹出包含扫描总数、成功/跳过/失败统计及逐本明细的 **批量处理报告**。

### 4. 包内指纹 `META-INF/typefolio.tag` 与免后缀识别
- 在生成对话版 EPUB 时同步写入轻量级包内标记 `META-INF/typefolio.tag`（记录版本号、类名 `tf-dlg`、语言及扫描/标注统计）。
- `BookContext` 与批处理扫描器同时支持识别 `.tf_dlg.epub` 文件名、`META-INF/typefolio.tag` 包内标记以及 `<span class="tf-dlg">` HTML 兜底探测：即使将导出或覆盖后的书籍重命名、移动目录，打开时仍可立即识别为已标注对话版并直接生效，避免重复加工。

---

## ⚙️ 新增配置与文档更新

- **新增全局设置键**：`typefolio_batch_settings`（记忆批量处理的源目录、输出模式、目标/备份目录、命名规则与扫描选项）。
- **文档与展示**：[README.md](file:///d:/code/typefolio.koplugin/README.md#L10-L33) 新增集成效果全景截图（`assets/typefolio_showcase.png`）及 3 步复现说明。

---

## 📦 安装与升级

1. 下载并解压发布包，将完整目录 `typefolio.koplugin` 覆盖复制到 KOReader 的 `plugins/` 目录下（如 `koreader/plugins/typefolio.koplugin`）。
2. 重启 KOReader 即可生效。

# v3.3.0 · 2026-11-24

# 文笺 (Type Folio) v3.3.0 Release Notes

> **版本定位**：智能对话副本无缝切换、对话深浅配色与专属字体、系统状态栏防误触锁定、界面去技术化全面收敛。

---

## 🌟 核心更新亮点

### 1. ⚡ 智能对话副本无缝切换与双向进度同步
* **开书自动探测与跳转**：打开未标注的原书时，插件自动检测是否存在对应的 `.tf_dlg.epub` 对话副本；若已开启自动打开，将直接无缝切入副本阅读，无需读者在文件管理器中手动翻找。
* **双向阅读进度实时同步**：
  * 打开或切换副本时，自动将原书的阅读进度（页码、百分比、书签与 XPointer 位置）同步至副本；
  * 在副本中退出或返回原书时，同样自动将最新进度无损回写至原书。
* **安全返回原书**：副本菜单提供「返回原书…」快捷操作，确认返回时自动暂停该书的自动跳转，保留随时切换自由。

### 2. 🎨 对话样式全面升级：字体深浅颜色与独立底色
* **字体颜色（5 档精选灰阶）**：支持将对话文字设为 `默认`、`纯黑`、`深灰`、`中灰`、`浅灰`，通过底层 CSS 高效注入，翻页零卡顿。
* **字体底色（独立调节）**：独立子菜单提供 `底色开启` 开关与 `浅灰` / `中灰` / `深灰` 3 档灰度选择，同时支持父菜单勾选框一键快速启闭。
* **对话字体、加粗与斜体**：自由指定设备已安装字体作为对话专属字体，勾选「字体斜体」，**人物台词自动呈现特色字效，而旁白叙述文字（如“他问我。”）严格保留原生宋体正文字形**！

### 3. 🛡️ 状态栏新增「禁用系统状态栏」防误触锁定
* **单手握持防误触**：在「状态栏」菜单中勾选 **「禁用系统状态栏」**，将一键隐藏 KOReader 原生底栏，并同步开启系统的「设置 → 状态栏 → 锁定状态栏」。
* **彻底告别误触弹窗**：在屏幕下边缘轻触翻页时不再触发系统底栏弹出；取消勾选时自动对称恢复原有状态栏模式并解除锁定。

### 4. 🧹 菜单全面「去技术化」与结构收敛
* **面向读者视角重塑术语**：彻底移除底层实现术语（如「按 class 标记着色」、「DOM 标记」等），全界面统一采用「对话样式」、「对话副本」等直观概念。
* **移除冗余选项**：精简正文与章节菜单，移除着重号与对话动态画笔入口，主菜单更加纯粹专注。
* **全新出版级展示大图**：README 迎来全新大字版 6 大排版特性全景示意海报，零文字遮挡、一目了然。

---

## 📋 详细更新日志

* **对话与副本管理**：
  * [新增] `tools/epub_dialogue_tagger.lua` 增加原书关联元数据，支持根据原书路径/哈希自动寻址对应 `.tf_dlg.epub`。
  * [新增] `main.lua` 增加 `onReaderReady` 钩子，开书自动探测副本并以 `UIManager:nextTick` 调度切换，避免阻塞主线程。
  * [优化] 阅读进度双向互通引擎：在开书与关闭时安全读取并写回 `ReaderSettings`。
  * [新增] 对话菜单精简为视觉样式（开关/字体/颜色/底色/加粗/斜体）与副本管理两段式结构。
* **状态栏**：
  * [新增] `core/koreader_settings.lua` 增加 `isSystemStatusBarDisabled` 与 `setSystemStatusBarDisabled` 接口。
  * [新增] 状态栏主菜单快捷项 `Disable system status bar`（禁用系统状态栏）。
  * [优化] `KOReaderSettings.syncNativeFooterBar` 适配：在锁定禁用状态下防止外部被动重绘。
* **正文与排版**：
  * [精简] 移除「正文与章节」中的着重号相关子菜单。
  * [优化] CSS 生成器支持 `color` 与 `background-color` 灰度变量精确渲染。
* **文档与多语言**：
  * [双语] `zh_CN.lua` 与 `en.lua` 补全所有新增对话参数与状态栏防误触词条。
  * [README] 重构排版特性展示图（超清大字版、避开文字零遮挡、页眉页脚合并说明）。

---

## 📦 安装与升级指南

1. 下载 Release 压缩包解压得到 `typefolio.koplugin` 文件夹。
2. 将其完整复制到阅读设备的 KOReader 插件目录（例如 `koreader/plugins/typefolio.koplugin`）。
3. 重启 KOReader 即可体验全新特性。

# v3.1.0 · 2026-08-30

# Release v3.1.0

## What's Changed / 变更说明

### 中文 (Simplified Chinese)
- **自定义底部页脚与状态栏**：新增基于 ViewModule 与 Blitbuffer 的独立绘制页脚，突破原生 ReaderFooter 限制，支持两端对齐、居中、古典页码与微型阅读进度条。
- **9 组精选设备与状态栏预设**：涵盖 Kindle、Kobo、Kobo 双端、掌阅、汉王、文石、微信读书、极简纯页码与现代全功能风格。
- **丰富插槽类型与分割线**：支持 12h/24h 时钟、章节名、书名、作者、动态电池图标与电量、组合进度、预计剩余时间、普通/古典页码、实线/虚线/点线/微型进度条等。
- **原生状态栏智能联动**：支持在插件内一键切换隐藏/显示 KOReader 原生顶部与底部状态栏，避免双重状态栏重叠。
- **菜单交互优化**：新增改动后实时预览机制（无缝接管层），优化关闭文档时的常驻窗口清理。
- **规范与工程化完善**：新增根目录 AGPL-3.0 LICENSE 文件，完善测试用例与打包过滤规则。

### English
- **Custom Bottom Footer & Status Bar**: Added standalone ViewModule and Blitbuffer rendering for footers, supporting justified/centered text, classical page numbering, and micro progress bars.
- **9 Curated Device & Status Bar Presets**: Includes Kindle, Kobo, Kobo Dual, iReader, Hanvon, BOOX, WeChat Read, Minimalist, and Modern layouts.
- **Rich Slot Items & Dividers**: Supports 12h/24h clocks, chapter title, book title, author, dynamic battery icons, combined progress, estimated reading time, classical page numbers, and custom divider lines/progress bars.
- **Native Status Bar Integration**: Seamlessly toggle native KOReader top/bottom status bars directly within the plugin to prevent overlap.
- **Menu Preview & Lifecycle Enhancements**: Added full-screen live preview with touch dismissal and improved window cleanup on document close.
- **Packaging & Compliance**: Added root AGPL-3.0 LICENSE file, expanded test specifications, and improved build packaging filters.

# v3.0.5 · 2026-08-17

# Release v3.0.5

## What's Changed / 变更说明

### 中文 (Simplified Chinese)
- **内置预设保护**：修复套用内置预设（如研读笔记）时静默关闭对话高亮、强调点与跳过引用块绘制器的问题。现在仅覆盖预设声明的字段，读者已调好的绘制器与个性化设置完整保留。
- **预设导入导出健壮性**：修复首字下沉倍数（`drop_caps.scale`）因浮点数被整数规则误拒导致无法跨设备导入的缺陷；补充标题边框居中与章节分页规则；加入显式 NaN 防护。
- **排版体检可视化标记**：修复体检问题标记画笔空转的问题。开启后可直接在页面上高亮标出「首字下沉首段全角空格」与「未开启跳过时的居中段落」。
- **跨页段落对话精准着色**：修复从上一页跨页续接的段落因偏移叠加导致引号着色错位的问题；改用语义索引清洗后的文本基准，彻底杜绝着色漂移。
- **对话高亮引擎与性能优化**：段落引号扫描改为单次执行多处共用；优化整句连续引号的快速着色通道；明确「有引号即高亮」的判定原则，真机实测对话召回率达 100%。
- **全页 HTML 预检与引用块跳过**：统一整页与逐行引用判定规则；引入整页结构化 HTML 预检机制，普通页面翻页原生调用开销降低约 95%，且对旧版 KOReader 自动兼容降级。
- **工程化与自动化测试**：新增 6 项针对预设套用、编解码校验、体检标记、跨页对话着色的自动化回归测试；提供标准的 Python 自动化打包脚本。

---

### English
- **Built-in Presets Protection**: Fixed an issue where applying built-in presets (e.g. Study Notes) inadvertently disabled dialogue highlights, emphasis marks, and blockquote skip painters. Presets now clone the current configuration and only override explicitly defined fields.
- **Preset Import/Export Robustness**: Fixed drop caps scale (`drop_caps.scale`) float rejection during import; added missing validation rules for centered heading borders and chapter page breaks; added explicit NaN guards.
- **Visual Health Check Markings**: Fixed non-rendering health check findings overlay. Visual markers now accurately flag leading full-width spaces under drop caps and unskipped centered paragraphs on the visible page.
- **Cross-page Dialogue Alignment**: Fixed highlighting offsets on paragraphs continued from previous pages caused by overlapping coordinate baselines; now references sanitized semantic index text.
- **Dialogue Highlighting Optimization**: Quote scanning is now performed once per paragraph; optimized fast-path rendering for single contiguous quotes; standardized full quote recall policy (100% recall on tested books).
- **Full-page HTML Precheck & Blockquote Skipping**: Unified page-level and line-level blockquote tag matching; introduced full-page HTML precheck to reduce native engine calls by ~95% on non-quote pages with graceful fallback for older KOReader versions.
- **Testing & Packaging**: Added 6 automated regression specs covering preset application, codec schemas, health check diagnostics, and dialogue offsets; included automated Python packaging script.

# v2.1.2 · 2026-08-06

# Release v2.1.2

## What's Changed / 变更说明

### 中文 (Simplified Chinese)
- **目录/章节跳转绘制崩溃修复**：直接绘制模式下对 `crengine` 行框及双页 `xpointer` 查询增加 `pcall` 护栏机制并校验指针有序性。跳转瞬间若原生侧无法提供稳态行框，自动跳过当前帧画线，彻底解决崩进 `ReaderView.paintTo` 渲染循环引发闪退的问题。
- **开书按书重写 CSS 状态**：在 `onReaderReady` 钩子中按当前书 `typefolio_config` 自动重写与同步 `99_typefolio.css`，避免多书切换导致样式相互污染；并在文档中补充单文件机制限制说明。
- **模式切换与参数校验优化**：切换至直接绘制模式时，若选中仅 CSS 支持的样式（如段落底线/强调词下划线）自动重置为无；自定义粗细弹窗增加正数与范围校验（上限 20px）。
- **菜单交互与文档/翻译补全**：所有子菜单弹窗、预设管理及使用指南完成后保持菜单打开状态（`keep_menu_open`）；完善 README 功能全景表与英文说明；补齐 `Save`/`Rename`/`Delete` 等双语翻译。

### English
- **Directory & Chapter Jump Crash Fix**: Added `pcall` safety guards and box boundary validations for `crengine` line boxes and dual-page `xpointer` queries in direct drawing mode. Silently skips invalid frames during chapter transitions to prevent crashes in `ReaderView.paintTo` loop.
- **Per-Book CSS Synchronization**: Rewrites and synchronizes `99_typefolio.css` using current book's `typefolio_config` in `onReaderReady`, preventing style cross-contamination across books. Updated README with single-file CSS limitations.
- **Mode Switching & Input Validation**: Automatically resets CSS-only underline styles when switching to direct paint mode. Added positive number range validation (max 20px) for custom line thickness input dialogs.
- **Menu Interaction & i18n Completion**: Preserved menu open state (`keep_menu_open`) across popup dialogs, preset management, and help guides. Fully updated README feature matrix and filled missing bilingual translation keys for UI buttons.
