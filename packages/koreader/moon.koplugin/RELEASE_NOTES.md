# v0.4.7 · 2026-10-30

## 月读 v0.4.7

KOReader 插件包：`book.koplugin-v0.4.7.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.6`：

#### 新功能

- :sparkles: (lockscreen): 海报可按最近阅读/添加排序，未齐资源跟锁屏次数重出 (aa6dbb5b)
- :sparkles: (rare): WordWise 释义与注音分流，修空格断词 (f10780f3)
- :sparkles: (meta): 每个源和 feature 增加 _meta.lua，启用页据此展示 (fa1f2bc0)
- :sparkles: (home): 首页组件支持上下左右外边距 (30043e7a)
- :sparkles: (home): 最近阅读卡片增加立体透视布局 (357ffc58)
- :sparkles: (themes): 主题色增加墨黑，彩屏可开彩色又保持字迹清楚 (7b44dc0e)
- :sparkles: (kindle): Kindle 书库的书支持编辑元信息 (f14f04a2)

#### 修复

- :bug: (ci): 修圆角截角色值崩溃，清 WordWise 废键与边界误伤 (82d14af3)
- :bug: (lockscreen): 熄屏别盖底栏，唤醒后刷新锁屏图 (4ba6e489)
- :bug: (wechat): 进度推不上时丢掉脏行，别拖死整源同步 (240f6db4)
- :bug: (reader): 开书恢复进度不再误触发翻页动画 (2996cc14)
- :bug: (themes): 柔和主题封面四角都圆，别再只有顶边圆底边方 (04dafe76)
- :bug: (reader): 扫盘根目录之外的 local 行不再当书架成员，修第三方插件章节弹结束页 (ab4d549d)

#### 性能

- :zap: (lockscreen): 立体封面复用梯形缓存，合成与未齐重试别堵主线程 (676c5863)

#### 重构

- :recycle: (source): kavita / bookorbit 并入内置源，去掉 ext 目录 (16e0bd3f)

#### 变更

- :children_crossing: (xray): 识别档位改为居中单选弹窗 (00cd46a1)
- :children_crossing: (setting): 根页增加游戏分组，空组不显示 (e975c970)
- :children_crossing: (setting): 桌面组分栏，页面收图书馆订阅书城统计 (26d1aac0)
- :children_crossing: (setting): 根页改成分组目录，阅读组再拆三类 (0a1bb33c)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.6...v0.4.7

# v0.4.6 · 2026-10-30

## 月读 v0.4.6

KOReader 插件包：`book.koplugin-v0.4.6.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

拓展书源（可选，需同时安装月读）：`moonsource-kavita.koplugin-v0.4.6.zip`（Kavita）、
`moonsource-bookorbit.koplugin-v0.4.6.zip`（BookOrbit）。解压后同样放进 `plugins` 目录。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.5`：

#### 新功能

- :sparkles: (home): 最近阅读可隐藏已读完 (02643d53)

#### 修复

- :bug: (reader): 库外文件不再登记接管，不弹「本书已读完」 (623e5952)
- :bug: (bluetooth): 关 Wi-Fi 带崩后按 wanted 自动拉起 (480b5450)
- :bug: (passcode): 横屏解锁临时竖屏，避免底行被裁 (26242322)

#### 变更

- :globe_with_meridians: (l10n): 补「✓ 隐藏已读完」英文与繁体翻译，修 CI (e3206237)
- :white_check_mark: (home): 覆盖最近阅读隐藏已读完 (21bc23dd)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.5...v0.4.6

# v0.4.5 · 2026-10-29

## 月读 v0.4.5

KOReader 插件包：`book.koplugin-v0.4.5.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

拓展书源（可选，需同时安装月读）：`moonsource-kavita.koplugin-v0.4.5.zip`（Kavita）、
`moonsource-bookorbit.koplugin-v0.4.5.zip`（BookOrbit）。解压后同样放进 `plugins` 目录。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.4`：

#### 修复

- :bug: (remote): 日志脱敏注释去掉源名，通过 feature 边界检查 (8585375f)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.4...v0.4.5

# v0.4.3 · 2026-10-29

## 月读 v0.4.3

KOReader 插件包：`book.koplugin-v0.4.3.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

拓展书源（可选，需同时安装月读）：`moonsource-kavita.koplugin-v0.4.3.zip`（Kavita）、
`moonsource-bookorbit.koplugin-v0.4.3.zip`（BookOrbit）。解压后同样放进 `plugins` 目录。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.2`：

#### 修复

- :bug: (fonts): 坏界面字体不再写进 fontmap 导致 KO 冷启动崩溃 (13b9459e)

#### 变更

- :green_heart: (fonts): fontpicker 测试适配 set 的成功返回值 (cc89afdc)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.2...v0.4.3

# v0.4.2 · 2026-10-29

## 月读 v0.4.2

KOReader 插件包：`book.koplugin-v0.4.2.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

拓展书源（可选，需同时安装月读）：`moonsource-kavita.koplugin-v0.4.2.zip`（Kavita）、
`moonsource-bookorbit.koplugin-v0.4.2.zip`（BookOrbit）。解压后同样放进 `plugins` 目录。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.1`：

#### 修复

- :bug: (xray): 有进展的全书分析不再误报失败 (#77) (07b454af)
- :bug: (insight): 显隐配置缺失时不再崩溃 (fca11c3d)
- :bug: (xray): 显式重新生成时释放已删实体的墓碑 (693216ba)
- :bug: (kavita): 卷行不全时不按「缺行=未读」聚合，退回服务端比例 (de45eb95)
- :bug: (kavita): 起始页只把云端位置当提示，合并交给 kamare (2a94d5f4)
- :bug: (kavita): 漫画进度跨设备取更靠后，书架百分比与打开位置同源 (d5234162)

#### 重构

- :recycle: (toc): 目录不做保鲜，开书与临近章末静默刷新 (0e7726a8)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.1...v0.4.2
