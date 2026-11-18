# v0.7.1 · 2026-11-18

## 月读 v0.7.1

KOReader 插件包：`book.koplugin-v0.7.1.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.7.0`：

#### 新功能

- :sparkles: (home): 首页文字封面改为独立选项，默认仍显示真实封面 (#140) (632e26fc)
- :sparkles: (home): 首页组件可全部删除，空配置不再回填默认 (#141) (6c6ffb0f)
- :sparkles: (reader): 追踪到期任务回调位置以辅助诊断阻塞 (c8fa0e6f)
- :sparkles: (animation): 翻页动画风格新增「不显示」，可免重启临时关闭 (#139) (80fffa19)

#### 修复

- :bug: (animation): 补上「不显示」繁中译文，并修复风格开关测试桩 (55d19366)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.7.0...v0.7.1

# v0.7.0 · 2026-11-17

## 月读 v0.7.0

KOReader 插件包：`book.koplugin-v0.7.0.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.6.5`：

#### 新功能

- :sparkles: (lockscreen): 实时主体和从未生成过的锁屏在锁屏瞬间同步生成 (808f3558)
- :sparkles: (lockscreen): 文字按背景明暗自动反色，设置改动改为手动刷新锁屏图 (485c09ab)

#### 修复

- :bug: (lockscreen): 没有划线时锁屏句子改用一言缓存和内置随机句 (8016b943)
- :bug: (toc): 目录不再被空列表覆盖，读库被打断时自动重读并联网重拉 (6265ca72)

#### 性能

- :zap: (toc) 目录冷读每批 16 章改为 256 章，避免大目录开书后长时间为空 (ff55f6eb)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.6.5...v0.7.0

# v0.6.5 · 2026-11-17

## 月读 v0.6.5

KOReader 插件包：`book.koplugin-v0.6.5.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.6.4`：

#### 新功能

- :sparkles: (setting): 启用的书源两列显示且已启用置顶 (#132) (6a427817)
- :sparkles: (ui): 主题列表支持多列排布 (406fab8c)
- :sparkles: (network): 新增休眠时自动关闭 Wi-Fi 开关 (91df481f)
- :sparkles: (wallpaper): 设置壁纸时底栏选中色可半透明 (2b964fa9)
- :sparkles: (bars): 替代系统栏时顶栏底栏背景透明 (44ffe4ec)
- :sparkles: (security): 安全页新增自动锁屏时间，同步 KOReader 自动休眠设置 (6a0ef484)
- :sparkles: (desktop): 长按底栏页签可换成自选图片，支持恢复默认 (eaf1801b)
- :sparkles: (ui): 图标与底栏支持图片图标，底栏格子可长按 (c532a907)
- :sparkles: (cover): 文字封面支持仅文字模式、白底黑字风格，标题过长可换列 (37675c55)

#### 修复

- :bug: (cover): 服务端 SVG 占位封面书名画不出，改用本地文字封面 (401aa233)

#### 界面

- :lipstick: (subscribe): 订阅页更紧凑，标题单行，已读空心圈 (486d3c5c)
- :lipstick: (ui): 单行文字视觉垂直居中，按钮文字不再偏上 (4d78afaf)
- :lipstick: (wallpaper): 界面壁纸预览改为等比缩放，不再宽度铺满 (5d749fc8)

#### 变更

- :globe_with_meridians: (security): 补充自动锁屏时间的英文与繁体译文 (27698d13)
- :globe_with_meridians: (desktop): 补充底栏自定义图标的英文与繁体译文 (81e2c4be)
- :globe_with_meridians: (cover): 补充文字封面设置项的英文与繁体译文 (5b26ecc5)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.6.4...v0.6.5

# v0.6.4 · 2026-11-17

## 月读 v0.6.4

KOReader 插件包：`book.koplugin-v0.6.4.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.6.3`：

#### 修复

- :bug: (iread): 目录翻页拼全；未入库的行（id 为 0）回书架取真实 id (4e8f0843)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.6.3...v0.6.4

# v0.6.3 · 2026-11-17

## 月读 v0.6.3

KOReader 插件包：`book.koplugin-v0.6.3.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.6.2`：

#### 修复

- :bug: (panel): 菜单排序前把函数型 text 纠正为 text_func，避免第三方菜单项拖垮下拉面板 (3905e94c)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.6.2...v0.6.3
