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

# v0.6.2 · 2026-11-17

## 月读 v0.6.2

KOReader 插件包：`book.koplugin-v0.6.2.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.6.1`：

#### 修复

- :bug: (panel): 物理键盘接入后重建菜单前还原 menu_items，修复下拉崩溃 (81defd06)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.6.1...v0.6.2

# v0.6.1 · 2026-11-16

## 月读 v0.6.1

KOReader 插件包：`book.koplugin-v0.6.1.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.6.0`：

#### 新功能

- :sparkles: (xray): 新增情节线事件时间线 (8303a68c)
- :sparkles: (tasks): 任务列表里已结束的任务支持长按删除 (c25bc6ff)
- :sparkles: (setting): 书库页加第三方书源插件二维码入口 (a2a8614d)

#### 修复

- :bug: (xray): 限制描述与别名长度，修复实体越扫越长 (23a2556f)

#### 变更

- :children_crossing: (xray): 设置页分为识别、画线两组，新增事件开关（默认关） (9acf79e5)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.6.0...v0.6.1

# v0.6.0 · 2026-11-16

## 月读 v0.6.0

正版书源已经全部移除，详情参考：https://moon.ankio.net/manual/library/sources/plugins

### 更新内容

相对上一版本 `v0.5.24`：

#### 新功能

- :sparkles: (scrape): 刮削内置多平台匿名搜索，不依赖书源插件 (e2efd58c)
- :sparkles: (reviews): 段评可借用多个来源，关联时选择来源 (d7bb3226)
- :sparkles: (extension): 第三方书源可复用旧 id，订阅页与刮削接入扩展挂点 (7cc1f20e)
- :sparkles: (xray): X-Ray 画线支持点状、位置、灰度、透明度，与段评共用样式配置 (87d84d88)

#### 修复

- :bug: (iread): 发现页分类里的无 url 分隔项不再导致响应无效 (ff8c67a5)
- :bug: (iread): 适配改版后的登录接口，账号校验改用 POST (39c2ac79)

#### 变更

- :white_check_mark: (source): 清理随书源迁出的测试，其余测试改用内置源 (56775f68)
- :fire: (source): 官方平台书源迁出为第三方插件 (78de7965)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.24...v0.6.0
