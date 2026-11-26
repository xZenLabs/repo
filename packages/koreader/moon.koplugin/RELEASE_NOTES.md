# v0.8.1 · 2026-11-26

## 月读 v0.8.1

KOReader 插件包：`book.koplugin-v0.8.1.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.8.0`：

#### 修复

- :bug: 修复模块加载器来源判断与数据源切换提示 (84daff3f)
- :bug: 修复模块加载器来源判断与数据源切换提示 (ec3a0e4b)

#### 界面

- :lipstick: (update): 更新日志经 md2html 转 HTML 渲染 (aef5e6c8)

#### 变更

- :fire: (setting): 删除书库页第三方书源插件扫码入口 (378fd8f3)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.8.0...v0.8.1

# v0.8.0 · 2026-11-26

## 月读 v0.8.0

KOReader 插件包：`book.koplugin-v0.8.0.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.7.2`：

#### 新功能

- :sparkles: (moon_sync): 同步书籍附属数据（X-Ray 与 AI 章节摘要） (1670fc4e)
- :sparkles: (translate): 翻译时选择粒度，并接上书中译文 (a900b5b8)
- :sparkles: (reviews): 关联书评可以按作者搜索 (214b3c6f)
- :sparkles: (reviews): 段评气泡透明度做成全局设置 (eb43fe99)
- :sparkles: (marketplace): 已安装插件可以停用和删除 (b550bd63)
- :sparkles: (moon_sync): 添加 WebDAV 月读同步 (22f1d979)
- :sparkles: (settings): 添加 WebDAV 同步设置入口 (1e2ad9a5)
- :sparkles: (db): 添加 sidecarBooks 查询月读同步书 (1d08eeec)
- :sparkles: (marketplace): 插件市场改为本地目录浏览安装 (13c8582c)
- :sparkles: (webdav): 支持关闭 1% 进度差阈值 (8d9cde6e)
- :sparkles: (convert): 新增通用 Markdown 转安全 HTML 转换器 (5aade455)
- :sparkles: (webdav): 上传阅读进度前检查远端版本 (4bfc9bdb)
- :sparkles: (zlib): 接入动态镜像目录、反爬识别与持久化钉住镜像 (50ec11db)
- :sparkles: (storage): 接入诊断文件清理页并修复列表确认框溢出 (2b38ff60)
- :sparkles: (storage): 新增 Kindle 存储转储文件扫描与删除 (a57188b0)
- :sparkles: (ui): 抽出横向下划线页签组件 (421ad9d5)
- :sparkles: (ui): 添加设置页面自定义导航栏与右侧动作图标 (54ee52a6)
- :sparkles: (reviews): 新增段评回复按钮位置设置 (1947f9a0)

#### 修复

- :bug: (reader): 章节目录适配器补 bookinfo，修在线书快捷面板目录崩溃 (#167) (6d72f888)
- :bug: (local): 换设备后失效书库目录引导重选，不再当同步失败 (b88a6ef4)
- :bug: (features): 每个 feature 只加载一次，加载失败的不再分发 (fc1ed661)
- :bug: (http): 续传重定向先判断再收头，跨主机不带 Authorization (213d6ac1)
- :bug: (bluetooth): 关不掉原生蓝牙时再试一次并提示重启 (b2ad5510)
- :bug: (local): 阅读章号按卷首对齐，长文件名改哈希 (964f693d)
- :bug: (wallpaper): 阅读壁纸时降级 REAGL，减轻翻页闪屏残影 (003baf08)
- :bug: (azw3): .mobi 也走 KF8 重建，修漫画 PDB 打不开 (cd4d059f)
- :bug: (reader): 条漫换章不再丢掉缩放和视图默认 (c5d7e592)
- :bug: (wallpaper): 阅读壁纸不再触发图片页全刷 (2bff90bc)
- :bug: (progress): 删除用 1% 判断同一阅读位置 (94ca3b68)
- :bug: (desktop): 目录名非 book.koplugin 时关书回桌面不再崩 (d4e7c0d2)
- :bug: (zlib): 去掉 iread.ink 错误的 HTTP Basic 门禁 (62150057)
- :bug: (ui): HtmlBox 透明叠画，TextViewer 支持 HTML 正文 (79524ecc)
- :bug: (fonts): 系统字体名含 %1 时预览不再崩页 (ee3f9c31)
- :bug: (legado): 修复书架时间戳与排序缺失导致书架展示乱序的问题 (a0bc2229)
- :bug: (wallpaper): 修复非全屏弹窗壁纸遮盖下层页面的问题 (ca0f2ec8)
- :bug: (lockscreen): 合成锁屏图前等待主体内封面落定，统计页封面不再只画占位 (49a3d2ec)

#### 界面

- :lipstick: (translate): 双语颜色和字号收成一张表单 (e1cc1fb0)

#### 性能

- :zap: (subscribe): DNS 结果缓存，目录复用旧锚点，解析输入截断 (87d2a6ea)
- :zap: (lockscreen): 合成后释放控件，壁纸释放位图，投屏节流 (f71fa14e)
- :zap: (desktop): 首页只构建一次，图书馆翻页复用旧页 (7ece9af1)
- :zap: (source): 本地扫盘与 Kavita 回填合成一次提交，远端回包先校验 (ebaf905c)
- :zap: (ui): 纯白 HTML 直贴，长列表只建当前页 (48c9cf4f)

#### 重构

- :recycle: (reader): 阅读侧功能减负，双语章改走挂点 (c1b490d2)
- :recycle: (utils): 收拢文件与文本工具，事务可嵌套，入口补 guard (65fb7f7d)
- :recycle: (moon_sync): WebDAV 连接改挂月读同步并自动搬迁 (bc567481)
- :recycle: (setting): 账号页按书源自己的分组展开 (d5e9fa7c)
- :recycle: (source): 重构本地源设置与进度接口 (cd02ba1d)
- :recycle: (progress): 开书前把精确位置交给进度 (e8dc0337)
- :recycle: (local): 本地进度只按静读天下的位置同步 (cc7a09f8)
- :recycle: (http): 合并 GitHub 镜像与 Release 探测并接入动态镜像目录 (a5b9539c)
- :recycle: (fonts): 重构字体管理与在线字体分类下载 (c77136a3)
- :recycle: (ui): 重构标题栏以支持右侧多个操作按钮 (f01f50cd)

#### 其他

- :wrench: (remote): 调整 WebDAV 设置与保存逻辑 (181da4b8)

#### 变更

- :fire: (remote): 删除远程管理投屏（屏幕镜像与点击注入） (8c00fe0e)
- :rewind: (reader): 恢复刷新诊断与 Lua 模块占用分析，诊断关闭时不挂钩子 (f5bc1a10)
- :globe_with_meridians: (l10n): 本地书源文案归回书源词典，删孤儿译文 (3e31d48c)
- :fire: (reader): 删除刷新诊断，开书身份只解析一次 (93f1b0f3)
- :children_crossing: (setting): 智能提到设置根目录 (8c9cf761)
- :children_crossing: (tasks): 后台任务一次清掉已结束记录 (c99ba111)
- :children_crossing: (store): 非混合时书城来源跟随当前书源 (4ba6a510)
- :white_check_mark: (remote): 设置接口测试补上月读同步分区 (a23b7ad7)
- :fire: (l10n): 删掉未使用的 AI 多接口文案 (c75ff225)
- :children_crossing: (setting): 书库组加上 Z-Library 和 OPDS 入口 (5bd51c15)
- :children_crossing: (lookup): 查词面板点击给出明确反馈 (#163) (d5233f74)
- :children_crossing: (marketplace): 插件下载可以转到后台 (18e260a3)
- :children_crossing: (desktop): 登录成功留在书源账号页 (514c8be1)
- :truck: (http): WebDAV 客户端从本地源挪到 http (7d57597f)
- fix(webdav): restore small progress changes and keep retry confirmation (d8fd197e)
- :children_crossing: (settings): 搜索不再展开动态长目录 (77fc7059)
- :lock: (install): 解压插件包时拒绝路径穿越 (e2dfea14)
- 🐛 (reviews): 段评标记/面板增加 generation 请求代号，防止旧异步回调覆盖新数据 (1f8c6bbd)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.7.2...v0.8.0

# v0.7.2 · 2026-11-19

## 月读 v0.7.2

KOReader 插件包：`book.koplugin-v0.7.2.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.7.1`：

#### 新功能

- :sparkles: feat: 锁屏海报墙可只用指定书源的书生成 (725b4242)
- :sparkles: feat: 混合模式封面左上角显示书源，可在图书馆封面设置关闭 (372c70b6)
- :sparkles: feat: 占位封面竖排书名中括号、标点与英文单词顺时针转 90° (45817db8)

#### 修复

- :bug: (toc): 空目录拉取失败不再每次翻页重试，目录重读加次数上限 (d5987fab)

#### 性能

- :zap: perf: 开书进度回调只重画弹窗面板，不再重复画遮罩与壁纸 (986f54f2)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.7.1...v0.7.2

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
