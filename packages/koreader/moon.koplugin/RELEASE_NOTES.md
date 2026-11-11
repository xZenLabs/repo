# v0.5.11 · 2026-11-11

## 月读 v0.5.11

KOReader 插件包：`book.koplugin-v0.5.11.zip`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

输入法词库（整库，手动 sideload）：`dictionary.sqlite3`（拼音）、`dictionary-wubi.sqlite3`（五笔）、`dictionary-cangjie.sqlite3`（仓颉）、`dictionary-zhuyin.sqlite3`（注音）。
下载对应布局的词库，直接放入 `koreader/.moon/`（与 `book.sqlite3` 同级），无需重命名。

### 更新内容

相对上一版本 `v0.5.10`：

#### 新功能

- 按书源清理本机数据，入口位于书库设置的账号下方；书籍索引和阅读记录分别选择，本地书与 WebDAV 分开处理，保留原书及远端数据。(`28265096`)
- 首页和锁屏的一言支持独立弹窗设置刷新间隔和句子类型。(`7b3088b1`)
- 一言一次拉取 20 条并从缓存抽取，支持按类型筛选。(`e71a96e3`)
- 书架刷新改为单击增量、长按全量。(`077c4b45`)
- 阅读快捷面板增加可重复执行的自动补目录。(`4bab78d2`)

#### 修复

- 用字节缓冲替代章节解密的逐字节数字表，降低解包内存峰值并修正内存预检。(`912e4a54`)
- 保留子进程退出码或终止信号，补充异常诊断，修复收尾时的误报。(`516e241f`)
- 修复数据与异步边界问题。(`a1643b66`)
- AI 漏翻时保留已译条目，只补缺失部分。(`7583456f`)
- 已保存的字体映射在加载时生效，避免开书后修改样式导致反复重载；同步更新测试。(`aeb342fb`, `a85c777c`)

#### 界面

- Kindle 缺少助手时直接进入账号页并提示安装。(`aeaa83e1`)
- 起点和 QQ 阅读分类筛选改用选中态。(`4ba3ae3c`)
- 缓存章节改为表单弹窗，范围使用固定档位单选。(`59a100e7`)
- 最近阅读设置改为设置弹窗。(`6dd199ac`)

#### 性能

- 折叠重复注解，避免开书时二次全量定位。(`38adea03`)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.10...v0.5.11

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
