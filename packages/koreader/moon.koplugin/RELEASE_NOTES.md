# v0.1.8

## 月读 v0.1.8

KOReader 插件包：`book.koplugin-v0.1.8.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.7`：

#### 新功能

- :sparkles: (ui): 优化 OPDS 设置界面 (4f995fa)
- :sparkles: (opds): 添加 OPDS 支持 (10b8efb)
- :sparkles: (ai): 更新翻页动画功能门面以绑定 Moon 自身的动画开关 (0dea1b8)
- :sparkles: (ai): 更新翻页动画功能门面以绑定 Moon 自身的动画开关 (aa7edf8)
- :sparkles: (ai): 优化书籍元数据同步逻辑 (c707a32)
- :sparkles: (ai): 优化书籍元数据同步逻辑 (2ffa99a)

#### 修复

- :bug: (http, ui, tests): 修复处理 Content-Length 为 0 的请求和 302 重定向逻辑 (6266e1f)
- :bug: (测试): 修正 system_spec.lua 中的测试逻辑 (c447ea8)
- :bug: (测试): 修正测试脚本中的内存拷贝逻辑 (bfbc311)

#### 重构

- :recycle: (lib): 加载 libz 库并初始化 inflate 函数 (ac74eb1)
- :recycle: (lockscreen): 适配混合模式 source_id 处理 (de59990)

#### 变更

- :fire: (ui): 优化封面下载处理逻辑 (5c3b479)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.7...v0.1.8

# v0.1.7

## 月读 v0.1.7

KOReader 插件包：`book.koplugin-v0.1.7.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.6`：

#### 修复

- :bug: (api): 修复登录及续期逻辑 (a93f9d6)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.6...v0.1.7

# v0.1.6

## 月读 v0.1.6

KOReader 插件包：`book.koplugin-v0.1.6.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.5`：

#### 新功能

- :sparkles: (ui): 优化界面样式和布局 (68a8fbd)
- :sparkles: (ui): 优化界面样式和布局 (44a9988)
- :sparkles: (ai): 添加本地 WebDAV 配置支持 (0660a3b)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (4ccd5a3)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (973f787)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (4ec65d2)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (edad981)
- :sparkles: (ui): 添加阅读页侧栏及配置选项 (86ddccc)
- :sparkles: (ai): 添加基于日出时间计算时区的功能 (dadc8cd)
- :sparkles: (ai) 优化封面图片加载逻辑 (a27bce4)
- :sparkles: (ui,feature): 更新多语言文本及同步阅读时间设置 (a071f43)
- :sparkles: (book): 实现书籍封面缓存功能 (d538fd7)
- :sparkles: (ui): 更新语言文件 (a767ae7)
- :sparkles: (ui): 添加书库刷新的假进度弹窗 (5082f0a)
- :sparkles: (db): 支持新旧身份合并及物理路径登记 (0eaad26)
- :sparkles: (ai): add WebDAV 支持 (d97ffb9)
- :sparkles: (ai): 支持处理 azw 文件格式 (98991ae)
- :sparkles: (ai): add AZW3 文档支持 (cbafe61)
- :sparkles: (ai): add AZW3 文档支持 (b647326)
- :sparkles: (ai): 更新 README 内容以反映新功能和改进 (7fff131)

#### 修复

- :bug: (ui,测试): 修复离线时注解同步逻辑 (30e778d)
- :bug: (http): 修复 Basic 认证问题 (4c48302)

#### 界面

- :lipstick: (ui): 添加分享锁屏图功能 (7bb0ffd)

#### 重构

- :recycle: (ui): 优化侧边栏显示逻辑 (5660c79)
- :recycle: (ui): 优化侧边栏翻页条布局 (0c82d0c)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.5...v0.1.6

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
