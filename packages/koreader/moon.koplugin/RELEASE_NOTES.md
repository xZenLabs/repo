# v0.5.10 · 2026-11-10

## 月读 v0.5.10

KOReader 插件包：`book.koplugin-v0.5.10.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.9`：

#### 界面

- :lipstick: (ime): 九宫格改为五列，左侧标点列并与手机拨号盘对齐 (eef73b6e)

#### 性能

- :zap: (fanqie): 读缓存目录不再整本扫锚点，刷新时保留已入库锚点 (487e6e6f)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.9...v0.5.10

# v0.5.9 · 2026-11-10

## 月读 v0.5.9

KOReader 插件包：`book.koplugin-v0.5.9.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.8`：

#### 新功能

- :sparkles: (notes): 远程管理新增高亮与笔记，左右分页并可弹窗改备注 (1369ab2d)
- :sparkles: (fonts): 在线字体列表缓存 30 天，关闭后隐藏在线分栏 (42d63ea4)

#### 修复

- :bug: (l10n): 去掉英/繁词典中重复的「高亮与笔记」键，并补上笔记接口文案 (76a13b7d)
- :bug: (reviews): 文档缺少排版指纹时不再在绘制标记时崩溃 (4aa7ba7e)
- :bug: (fanqie): 目录按卷分层并收录章内锚点 (97aa154f)
- :bug: (store): 彻底删除后失效残缺书城缓存并记录删除日志 (2aa008c3)

#### 性能

- :zap: (chapter): 已缓存章节切章时只登记路径，不再拉目录或重渲 (f0b416fd)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.8...v0.5.9

# v0.5.8 · 2026-11-10

## 月读 v0.5.8

KOReader 插件包：`book.koplugin-v0.5.8.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.7`：

#### 新功能

- :sparkles: (remote): 提取日志记录当前启动模式 (067a2ae9)
- :sparkles: (reader): 添加漫画 CBZ/CBT 默认排版 (91c15c57)

#### 修复

- :bug: (wechat): 修复发版测试：章节解包提示改走书源翻译 (85187873)
- :bug: (sync): 唤醒后 connection refused 视为网络未就绪并延迟重试 (a1fc6b8d)

#### 性能

- :zap: (wechat): 章节解包前预检内存 (efd2097c)
- :zap: (fonts): 字体下载写入过程日志，转换前预检内存 (d120120d)
- :zap: (utils): 增加内存预检，不足时可改用 no-framework 重启 (91d4ddb0)

#### 重构

- :recycle: (log): 启动日志打印字符画并记录启动模式，移除调试开关 (821a926a)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.7...v0.5.8

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
