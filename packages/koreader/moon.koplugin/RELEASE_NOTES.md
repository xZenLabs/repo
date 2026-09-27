# v0.1.5

## 月读 v0.1.5

KOReader 插件包：`book.koplugin-v0.1.5.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.4`：

#### 新功能

- :sparkles: (utils): 更新自动灯光周期配置 (5599759)
- :sparkles: (ai): 新增 WebDAV 连接测试功能 (bb9cce8)
- :sparkles: (ai): 添加翻页动画样式选项并更新测试 (8c79cf8)
- :sparkles: (ai): 添加翻页动画风格设置功能 (0096c30)
- :sparkles: (ai): 添加翻页动画风格设置功能 (b617680)
- :sparkles: (ai): 添加翻页动画风格设置功能 (fe3182c)
- :sparkles: (ai): 添加翻页动画风格设置功能 (f72592a)
- :sparkles: (ai): 添加和更新翻页动画样式 (422cd1b)
- :sparkles: (ai): 添加翻页动画补丁和国际化支持 (7d9d05f)

#### 界面

- :lipstick: (ui): 优化设置界面的按钮行为 (538fd5a)

#### 重构

- :recycle: (ui, tests): 优化首页组件数据刷新逻辑 (7414235)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.4...v0.1.5

# v0.1.4

## 月读 v0.1.4

KOReader 插件包：`book.koplugin-v0.1.4.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.3`：

#### 新功能

- :sparkles: 优化京东读书目录和章节下载逻辑 (fc856ea)
- :sparkles: (ui): 更新界面语言和设置项 (033e2f9)
- :sparkles: (ui): 添加背景遮罩功能 (eb127fc)
- :sparkles: (ai): 添加自动亮度和夜间模式功能 (a704971)
- :sparkles: (ai): 添加自动亮度和夜间模式功能 (f537081)
- :sparkles: (ai): 添加自动夜间模式功能 (b9129d6)

#### 界面

- :lipstick: (ui): 优化锁屏背景图绘制逻辑 (fa9e558)
- :lipstick: (ui): 优化锁屏背景图绘制逻辑 (e774100)
- :lipstick: (ui): 优化夜间模式下的 MeshMask 组件显示 (0618e6a)

#### 重构

- :recycle: (ui): 修复 reader_bar.lua 和测试中的 ReaderUI 状态处理 (ea42970)
- :recycle: (source): 修改章节缓存请求间隔参数 (bcfdd92)
- :recycle: (source): 修改章节缓存请求间隔参数 (1f4a99b)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.3...v0.1.4

# v0.1.3

## 月读 v0.1.3

KOReader 插件包：`book.koplugin-v0.1.3.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.2`：

#### 新功能

- :sparkles: (ai): 更新多语言文本和微信读书章节解析逻辑 (abfb7df)
- :sparkles: (ai): 新增连续章节模式全书笔记列表功能 (54040bb)
- :sparkles: (ai): 添加和更新本地化文本以及优化微信客户端逻辑 (7411f2e)
- :sparkles: (ai): enhance localization and API interaction for WeChat读书插件 (0dd7747)
- :sparkles: (ui): 添加桌面整页重画等待刷新完成的功能 (4ca670d)
- :sparkles: (update): 添加 GitHub Release 下载镜像加速功能 (14be457)

#### 修复

- :bug: (remote): 修正下载解析和配置保护逻辑 (53b3246)

#### 重构

- :recycle: (auth): refactor wechat authentication logic (6c70b74)

#### 其他

- :wrench: update files 项目级 MCP 配置（含 token） (e2ecf3c)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.2...v0.1.3

# v0.1.2

## 月读 v0.1.2

KOReader 插件包：`book.koplugin-v0.1.2.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.1`：

#### 新功能

- :sparkles: (ui): 改进图书馆筛选界面，实现分页显示功能 #31 (730c7a0)
- :sparkles: (test): 添加测试用例以验证进度帧的顺序处理 (b00e341)
- :sparkles: (ui): 改进输入法词库下载进度条显示逻辑 (8b2359c)
- :sparkles: (ai): 优化下载进度显示功能 (db938ba)
- :sparkles: (settings): 添加书友交流群按钮 (9a86b62)

#### 修复

- :bug: (fanqie): fix book detail fetching and reconciliation logic (422691b)
- :bug: (ui): 修复桌面手势被文件管理器抢先消费 (227ee99)
- :bug: (ui): 修复底栏点按被默认前光手势吞掉的问题 (0752b71)
- :bug: (remote): 移除覆盖写入对受保护路径的拦截 (1a7cf70)
- :bug: (font): 修复字体 id 处理与重复注册误判 (6c0a027)

#### 重构

- :recycle: (ui): 拆分行为设置并修复顶栏宽度缓存 (fb069c5)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.1...v0.1.2

# v0.1.1

## 月读 v0.1.1

KOReader 插件包：`book.koplugin-v0.1.1.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.0`：

#### 新功能

- :sparkles: (book): 新增缓存状态判断并调整详情页操作 (a79f9df)
- :sparkles: (book): 添加已下载筛选与单书缓存清理 (c66d732)
- :sparkles: (ui): 在首次渲染前写入顶栏偏好 (d1a022e)

#### 性能

- :zap: (utils): 转换微信读书字体为 sfnt 以降低内存 #12 (18b4035)
- :zap: (utils): 转换微信读书字体为 sfnt 以降低内存 (401cda1)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.0...v0.1.1
