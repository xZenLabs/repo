# v0.5.7 · 2026-11-10

## 月读 v0.5.7

KOReader 插件包：`book.koplugin-v0.5.7.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.6`：

#### 新功能

- :sparkles: (library): 详情页按文件后缀显示 WebDAV 书籍格式 (a7f703e3)

#### 修复

- :bug: (store): OPDS 源打开即拉根目录，不再只能搜索 (a994fc66)
- :bug: (wechat): 规范 xpointer 路径，映射失败时按章内比例上报进度 (30c3824a)

#### 性能

- :zap: (webdav): 优化硬刷新列目录并发与深度列表 (42520024)
- :zap: (wechat): 章节下载改为官方五章一批，缓存全书走 offline=1 (f2f0b761)

#### 重构

- :recycle: (reader): 抽取章节缓存至共享模块并注册快捷面板动作 (ff22e41e)
- :recycle: (reader): 抽取章节缓存至共享模块并注册快捷面板动作 (7f6a875d)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.6...v0.5.7

# v0.5.6 · 2026-11-09

## 月读 v0.5.6

KOReader 插件包：`book.koplugin-v0.5.6.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.5`：

#### 新功能

- :sparkles: (subscribe): 推荐源改接奇睿 API，去掉精选并修多级导航 (9542dff4)

#### 修复

- :bug: (subscribe): 修复 v0.5.6 发版测试：奇睿 catalog 用例与 l10n 归属 (9a527ecf)
- :bug: (wechat): 纯图章进度坐标可上报阅读进度 (0d4cde98)
- :bug: (desktop): 修复返回键无法退出桌面 (#114) (ad98a4dc)

#### 界面

- :lipstick: (subscribe): 推荐源显示描述，加入后不关窗并 toast (615e4b74)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.5...v0.5.6

# v0.5.5 · 2026-11-09

## 月读 v0.5.5

KOReader 插件包：`book.koplugin-v0.5.5.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.4`：

#### 修复

- :bug: (features): 更新后重登改走扩展点，下层不再 require features (eea60c6d)
- :bug: (features): 更新后按磁盘版本重登约定文件，壁纸不必重启才出现 (ae23ca7f)
- :bug: (setting): 去掉我的设备里重复的使用指南 (0a6028e8)

#### 界面

- :lipstick: (library): 封面圆角从逻辑 12px 收到 6px (b404820e)

#### 变更

- :children_crossing: (battery): 用法统计按唤醒/休眠/充电分段显示 (33293716)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.4...v0.5.5

# v0.5.4 · 2026-11-09

## 月读 v0.5.4

KOReader 插件包：`book.koplugin-v0.5.4.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.3`：

#### 新功能

- :sparkles: (library): 文件夹用最近阅读封面，并支持封面圆角 (7accc60f)
- :sparkles: (panel): 连续章节快捷面板可手动刷新目录 (7a62589b)

#### 修复

- :bug: (panel): 刷新目录 available 不因会话桩缺方法崩掉 (40a17713)
- :bug: (source): 番茄换号重推书架，取消目录刷新不吃迟到回包 (a77157bd)
- :bug: fix(source): 换账号保留书架和阅读记录 (0f0c0900)
- :bug: (insight): 软删除与下架的已读书仍计入读完 (7b767be7)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.3...v0.5.4

# v0.5.3 · 2026-11-09

## 月读 v0.5.3

KOReader 插件包：`book.koplugin-v0.5.3.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.2`：

#### 修复

- :bug: fix(source): 隔离临时文件并统一 Cookie 更新 (8c65c782)
- :bug: (qidian): 扫码合并书架 Cookie，VIP 不再假报失效 (f24ab548)
- :bug: (copymanga): 登录后落盘密码，401 才能自动重登 (17c5af19)
- :bug: (paths): Android 临时文件改落 .moon/cache/tmp (19c9d7a2)
- :bug: (desktop): 桌面手势 Dispatcher 动作落到 FM 模块 (97130e48)

#### 变更

- :see_no_evil: chore: 停止跟踪本地审计报告 (d1308a53)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.2...v0.5.3
