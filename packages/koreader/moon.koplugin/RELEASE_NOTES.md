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

# v0.1.0

## 月读 v0.1.0

KOReader 插件包：`book.koplugin-v0.1.0.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.0.9`：

#### 新功能

- :sparkles: (reader): 优先使用备用目录生成自动目录 (f099313)
- :sparkles: (reader): add 整书模式自动目录扫描 (9d17b4d)
- :sparkles: (reader): add 整书模式自动目录扫描 (c0c8037)
- :sparkles: (moon): 根据 Content-Length 显示下载进度 (5ef3a57)

#### 修复

- :bug: (http): 提高连接超时默认值并移除局部覆盖 (9ba88e9)
- :bug: (http): 修复异步连接失败时 DNS 缓存与错误提示 (845c198)
- :bug: (popup): 修复多选时误触发关闭回调 (721cdea)

#### 界面

- :lipstick: (ui): 迁移设置弹窗并添加菜单遮罩 (95e8ba4)

#### 性能

- :zap: (reader): 限制高亮菜单与选区刷新区域 (9ede23c)

#### 其他

- :wrench: (remote): 设置 kind 为 light (f038a47)

#### 变更

- :white_check_mark: (remote): 补充 workers.job.run 参数校验断言 (a16bbb0)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.0.9...v0.1.0

# v0.0.9

## 月读 v0.0.9

KOReader 插件包：`book.koplugin-v0.0.9.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.0.8`：

#### 新功能

- :sparkles: (wechat): 对齐阅读时长上报与划线定位 (dae1664)
- :sparkles: (ime): 添加小鹤双拼输入支持 (3ec0d74)
- :sparkles: (ime): 添加小鹤双拼输入支持 (e252b2a)
- :sparkles: (ui/image): 添加图片组件夜间反色选项 (c8b0b77)
- :sparkles: (remote): 增加空闲自动关闭远程服务 (3ad80d0)
- :sparkles: (lockscreen): 增加海报墙多种布局风格并移除书架组件 (002f242)
- :sparkles: (lockscreen): 显示生成中状态并刷新锁屏预览 (db38b6c)
- :sparkles: (source): 完善缓存队列与同步失败反馈 (4cfc443)
- :sparkles: (ui): 添加 BookOrbit 同步快捷动作 (6b5a340)
- :sparkles: (ui): 新增阅读方向快捷动作 (fc9f643)
- :sparkles: (local): 支持 WebDAV 异步扫描 (80a0e0d)
- :sparkles: (local): 添加本地文件上传同步 (e09a0d1)
- :sparkles: (source): 添加 WebDAV 书源支持 (14d79f4)
- :sparkles: (xray): 添加下划线样式设置与刷新动作 (2ca4e20)
- :sparkles: (font): 应用字体设置时校验生效状态 #12 (ba82327)
- :sparkles: (lockscreen): 新增锁屏标题单行适配并清理 AI thinking 字段 (a11e89f)
- :sparkles: (lockscreen): add single-line title fitting for bills and receipts (3020411)
- :sparkles: (settings): 新增清除当前源本地阅读统计 (cc912b0)
- :sparkles: (ui): 添加划词手柄并移除顶栏刷新状态 (86139fb)
- :sparkles: (ui): 添加设置叠层与阅读栏自定义 (ae48af0)
- :sparkles: (jdread): 新增京东读书章节远程图片本地化 (18eae54)
- :sparkles: (jdread): 新增京东读书章节远程图片本地化 (199960b)
- :sparkles: (jdread): 新增京东读书章节远程图片本地化 (ae64ab1)
- :sparkles: (jdread): 异步本地化章节资源并支持取消 (dbafabb)
- :sparkles: (jdread): 支持新阅读器目录与章节下载 (9983b6a)
- :sparkles: (fanqie): 改用番茄 App reading API 拉取正文 (4c1b45d)
- :sparkles: (fanqie): 改用番茄 App reading API 拉取正文 (97f9dce)
- :sparkles: (remote): 添加截图远程分享二维码按钮 (b6a4551)
- :sparkles: (settings): 新增屏幕刷新与彩色渲染选项 (5fc64b4)
- :sparkles: (host): 添加首次安装启动项种入逻辑 (5db5487)
- :sparkles: (source): 添加番茄小说数据源 #29 (6152cf7)
- :sparkles: (ui): 将混合模式开关移至当前活跃源分区顶部 (6ad83b0)
- :sparkles: (library): 支持按数据源筛选混合书籍 (a620dcd)
- :sparkles: (catalog): 支持混合模式跨源聚合 (f9d6a47)
- :sparkles: (settings): 新增书库混合模式开关 (8331521)
- :sparkles: (ui): 隐藏混合模式下的源名槽位 (1dec9c8)
- :sparkles: (ui): 添加图书馆筛选和排序功能 (91bb523)
- :sparkles: (ui): 添加墨水屏网状遮罩组件 (1a98927)
- :sparkles: (ui): 添加左右翻页容器组件 (be2120e)
- :sparkles: (ui): 添加书籍打开状态提示与交互优化 (1c0d3c2)
- :sparkles: (book): 增加打开书籍的异步回调支持并添加多语言支持 (15c2c50)
- :sparkles: (ui): 添加封面打开中提示条组件 (5b82a51)
- :sparkles: (ui): 增加书籍封面右下角「更多」标志及交互功能 (74bb2ba)
- :sparkles: (ui): 添加最近阅读列表中封面标题的显示/隐藏功能 (f0b2628)
- :sparkles: (ui): 添加最近阅读书架行数和列数设置功能 (322b8a9)
- :sparkles: (ui): 添加首页组件设置功能 (c4c6117)
- :sparkles: (ui): 添加快捷面板现场编辑功能 (fc22e09)
- :sparkles: (ui): 添加顶栏刷新状态组件 (119385f)
- :sparkles: (ai): 更新 KOReader 版本门槛为月发号格式并添加适配器验证 (f69207a)
- :sparkles: (ui): 添加首页翻页条组件 (e19dfa6)
- :sparkles: (hitokoto): 添加一言随机选择逻辑 (b4acc72)
- :sparkles: (ui/desktop): 新增“历史上的今天”与“热点新闻”桌面组件 (8247b1a)
- :sparkles: (ui): 重构天气组件布局，优化信息展示与图标管理 (b404d90)
- :sparkles: (ui): 添加桌面首页天气组件 (f6f75c8)
- :sparkles: (book/image): 新增网络图片下载队列与磁盘缓存模块 (7856687)
- :sparkles: (book.koplugin): 新增在线内容获取模块 (ab21eb7)
- :sparkles: (http): 支持 GET 请求缓存 (0737d04)
- :sparkles: (ui): 增加生命周期任务与 HTTP 句柄取消支持 (36ff6a2)
- :sparkles: (ui): 增加生命周期任务与 HTTP 句柄取消支持 (bc582c3)
- :sparkles: (ui): add lifecycle support and docs (13044f1)
- :sparkles: (ui): 新增 KOReader 生命周期基类 (55f7d80)
- :sparkles: (ui): 添加自动亮度支持 (04b3c33)
- :sparkles: (ui): 添加自动亮度支持 (239e59a)

#### 修复

- :bug: (local): 修复 Moon+ Reader 进度格式与整书折算 (0d1cfe6)
- :bug: (auth): 细化京东登录二维码校验错误 (84ce1cc)
- :bug: (desktop): 优先转发文件管理器已配置手势 (aae0949)
- :bug: (ui): fix night mode color display (1e22c34)
- :bug: (ui): 修复 Source 激活回调调用方式 (3f8c638)
- :bug: (sync): 修复统计重复推送与文件同步错误 (4d8cbd8)
- :bug: 修复书架同步与缓存边界问题 (209dfdc)
- :bug: 修复远程路径、注解快照与亮度换算 (444afee)
- :bug: (plugin): 修复文件写入与状态回调错误处理 (21fa854)
- :bug: (book): 修复目录缓存过期与删除计数不一致 (891e260)
- :bug: (local): 传递本地扫描错误并区分跳过状态 (3a443be)
- :bug: (book): 修复空封面覆盖并支持本地封面回退 (d9792f1)
- :bug: (reader): 修复唤醒阅读器时原生栏状态被恢复 #8 (c1773d3)
- :bug: (font): 修复偏好比较触发字体注册 #12 (951fbe9)
- :bug: (moon): 修复全刷设置覆盖与章节快开进度误用 (82d16fd)
- :bug: 修复本地书籍元数据补齐与字体安装检测 (5684b6d)
- :bug: (http): 清理取消请求后的超时与回调 (d47b33a)
- :bug: (desktop): 修复首页换页误销毁设置页生命周期 (ab03b82)
- :bug: (ui): 修复页面指示器按钮颜色显示问题 (e05d702)
- :bug: (ui): 统一阶段入口日志记录 (ace8f43)
- :bug: (ui): 改进自动亮度传感器探测与 LIPC 生命周期 (a4f4d22)

#### 界面

- :lipstick: (ui): 统一 Z站 文案并优化卡片与详情交互 (f8b582c)
- :lipstick: (ui): 替换首页编辑叠层的遮罩实现 (d8995ab)

#### 性能

- :zap: 缓存 DNS 解析并让出输入轮询 (9041e50)

#### 重构

- :recycle: 清理废弃接口并重构缓存与主页视图 (327d45a)
- :recycle: 清理废弃接口并重构缓存与主页视图 (a2d8ab7)
- :recycle: 清理废弃接口并重构缓存与主页视图 (1dfad36)
- :recycle: (source): 抽取目录缓存与书架同步模块 (15cfc4d)
- :recycle: (source): 统一章节目录缓存并完善错误处理 (3f958bf)
- :recycle: (crypto): 迁移 AES 模块到公共目录 (15c4645)
- :recycle: (page_turn_animation): 移除刷新率强制拦截并改为默认设置 (e085d9e)
- :recycle: (fanqie): 重构书架详情与模块依赖 (7df486e)
- :recycle: (types): 将类型定义迁移到业务模块 (d361a3a)
- :recycle: (update): 将更新检查移至桌面 Resume (3c15949)
- :recycle: (fanqie): 重构字符解码控制流 (7898b3d)
- :recycle: (remote): 将截图分享入口迁移至 remote 模块 (010ebaf)
- :recycle: (remote): 将截图分享入口迁移至 remote 模块 (9306ba0)
- :recycle: (plugin): 移除旧版兼容 API 并统一取消方法 (6fc9bc9)
- :recycle: (plugin): 统一插件生命周期并清理历史兼容 (bca8d61)
- :recycle: (fanqie): 重构番茄源并迁移旧配置与缓存 (8fc58bf)
- :recycle: (fanqie): 重构番茄小说网络层为异步回调 (0667bd2)
- :recycle: (book): 重构书架删除与进度同步模型 (aa2c3bb)
- :recycle: (ui): 重构统计页为本地聚合读取 (f558e2a)
- :recycle: (ui): 将混合模式并入数据源选择器 (edb5548)
- :recycle: (ui): 将混合模式并入数据源选择器 (1125e7f)
- :recycle: (store): 将书城改为可选 Z-Library (dddd505)
- :recycle: (ui): 拆分书籍详情模块并引入来源参数 (279e7d2)
- :recycle: (ui): 替换弹窗关闭逻辑为 Lifecycle 管理，重构详情页工具栏布局 (4334446)
- :recycle: (ui): 重构首页布局逻辑，改为按真实屏幕高度初始化默认分页 (4e92998)
- :recycle: (ui): 重构书城页面大小同步逻辑 (1b16fe8)
- :recycle: (ui): 修复桌面端书籍信息点击事件参数不一致问题 (34ddebc)
- :recycle: (ui): 重构桌面生命周期管理，精简 Start 阶段并优化离屏加载逻辑 (8e90bab)
- :recycle: (ui): 修复底栏更新时未触发重绘的问题 (aa82f02)
- :recycle: (ui): 重构图书馆界面，支持平铺封面书架和筛选搜索功能 (37bbf40)
- :recycle: (ui): 优化首页编辑叠层手势处理逻辑 (85cd76e)
- :recycle: (ui): 调整统计卡片高度计算逻辑以适配实际文字尺寸 (d42e5dc)
- :recycle: (ui): 调整布局逻辑，移除组件自动填充剩余空间的行为 (643618e)
- :recycle: (ui): 将页面条组件的文本按钮替换为图标按钮 (3e68bda)
- :recycle: (ui): 优化首页组件生命周期管理与内存释放 (b3b4e20)
- :recycle: (ui): 调整引言块布局为上下结构并优化高度计算 (fe6bdb7)
- :recycle: (ui): 重构引言块布局，改为左引号+正文+右署名格式 (d542a63)
- :recycle: (ui): 重构引言块布局，改为左引号+正文+右署名格式 (a5500f9)
- :recycle: (ui): 优化引言组件与首页布局逻辑 (a48e5dc)
- :recycle: (ui): 优化引言组件布局与高度计算逻辑 (f27778e)
- :recycle: (ui): 重构首页布局系统，统一使用内容高度规范和 fill 填充逻辑 (74b7ac8)
- :recycle: (ui): 调整首页刷新逻辑，将刷新事件传递给天气子视图处理 (fb7dd44)
- :recycle: (ui): 重构 Desktop 生命周期与事件分发逻辑 (c765135)
- :recycle: (ui): 重构桌面组件，将 stats 改名为 insight 并优化页面切换逻辑 (ce7c089)
- :recycle: (ui): 重构 refresh.lua 中的 Widget 返回结构 (d814747)
- :recycle: (ui): 修复顶部栏布局高度计算错误 (18f678c)
- :recycle: (ui): 更新桌面界面初始化逻辑并添加日志信息 (eebb093)
- :recycle: (ui): 重构UI组件继承结构，统一使用View基类 (7a4d8ab)
- :recycle: (ai): 重构插件内部结构与依赖，增强稳定性与可维护性 (c5f6345)
- :recycle: (ui): 重构桌面界面组件引用路径 (978245e)
- :recycle: (ui): 统一顶部栏组件的构建逻辑与生命周期管理 (4f452d6)
- :recycle: (ui): 重构顶栏项目基类以支持更灵活的UI管理 (f7b9497)
- :recycle: (ui): 重构界面组件以使用新的构建模式 (d8cf681)
- :recycle: (ui): 重构底栏组件为面向对象结构 (c08f713)
- :recycle: (ui): 优化设置行组件注释和参数说明 (1a909f8)
- :recycle: (ui): 优化图标组件代码结构 (aff8d0b)
- :recycle: (ui): 优化页码处理逻辑，增加 clamp 函数限制页码范围 (1963e32)
- :recycle: (ui): 重构 surface 组件以支持胶囊形状和卡片形状 (34ba3c8)
- :recycle: (ui): 为 chart.lua 文件添加类型注释定义 (f2a9ba4)
- :recycle: (ui): 为 bookui.lua 添加类型注释定义 (ac624e8)
- :recycle: (ui): 优化图片下载与解码逻辑 (f544ced)
- :recycle: (ui): 重构顶栏组件生命周期管理 (d21abed)
- :recycle: (ui): 重构桌面视图构建逻辑，分离壳与内容，优化生命周期管理 (d518a50)
- :recycle: (ui): 优化生命周期阶段补齐逻辑 (b717475)
- :recycle: (ui): 优化生命周期管理避免内存泄漏 (d296522)
- :recycle: (ui): 完善生命周期管理逻辑 (d525f2c)
- :recycle: (utils): 优化日志写入机制与调试输出 (35f3fd2)
- :recycle: (ui): 优化生命周期类构造函数逻辑 (aac9d61)
- :recycle: (ui): 重构首页子组件基类逻辑 (78f332b)
- :recycle: (ui/desktop/home): 重构首页组件架构，将时钟拆分为独立子组件 (e0c1767)
- :recycle: (main): 重构主入口，拆离阅读/锁屏/远程模块 (cd29c61)
- :recycle: (ui): 重构顶栏项生命周期与刷新机制 (e68d69e)
- :recycle: (ui): 重构顶栏生命周期与重建逻辑 (7721036)
- :recycle: (ui): 重构桌面页重建逻辑 (6528536)
- :recycle: (ui): 使用泛型改进生命周期返回类型 (2188e9a)
- :recycle: (ui): 使用泛型改进生命周期返回类型 (56ea15e)
- :recycle: (ui): 重构 Lifecycle 构造并同步文档 (633576b)
- :recycle: (ui): 重构 Lifecycle 构造以支持传入对象 (83fe4a1)
- :recycle: (ui): 重命名 uiAvailable 为 uiReady 并新增 Alive 方法 (4c64ed1)
- :recycle: (ui): 重构桌面生命周期与组件化状态 (afb43ca)
- :recycle: (ui): 重构顶栏为生命周期组件 (3f61881)
- :recycle: (workers): 重构 worker 调度与内存并发计算 (e1bfb17)
- :recycle: (workers): 重构任务调度并增加内存限流 (8583bf9)
- :recycle: (workers): 重构任务调度并增加内存限流 (bb36f83)
- :recycle: (http): 抽取 Turbo 泵与补丁并简化请求流程 (6578a35)
- :recycle: (workers): 简化任务模型并移除 SimpleJob (2d04691)

#### 文档

- :memo: (docs): 同步项目文档与当前实现 (f5b3e81)
- :memo: (types): 完善 LuaLS 类型注解与 FFI 桩 (610adcf)
- :memo: (types): 完善 LuaLS 类型注解与 FFI 桩 (05bcef5)
- :memo: (docs): 拆分设计文档为模块契约 (c84a568)
- :memo: (l10n): 添加英文和繁体中文翻译项 (9f9cc9d)
- :memo: (ui): 补充 Lua 类型注释和详细字段说明 (c1a3d7a)
- :memo: (ui): 添加 BookPager 和 BookPopup 类型注释 (f669eab)
- :memo: (ui): 更新桌面 UI 生命周期注释 (8e4b83d)

#### 其他

- :wrench: : update .gitignore for backup files and moon directory (79ec0e5)
- :wrench: update files (1c2d7df)
- :wrench: (http): 为 pump 补充空 stop 函数 (eb77aaf)

#### 变更

- :white_check_mark: (tests): 添加 widget 桩并修正 overlapgroup 路径 (6378581)
- :fire: (ui): 移除阅读方向快捷动作 (31c484e)
- :fire: 移除日志器启动调用及相关测试桩 (5fb6ab9)
- :white_check_mark: (tests): 补充章节远程图片与阅读器设置栏测试 (2d83c1b)
- :white_check_mark: (tests): 补充章节远程图片与阅读器设置栏测试 (98b5fc2)
- :white_check_mark: (tests): 补充章节远程图片与阅读器设置栏测试 (96b0966)
- :coffin: (book): 移除返回桌面时旋转主屏逻辑 (7216d97)
- :fire: (ui): 移除旧的弹窗和顶栏组件，引入新的视图架构 (f541b42)
- :fire: (ui): 移除所有首页组件代码 (a6b4f02)
- :adhesive_bandage: (ui): 修复时钟组件在日历对象不存在时的空指针异常 (d557f46)

- （无提交记录）

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.0.8...v0.0.9

# v0.0.8

## 月读 v0.0.8

KOReader 插件包：`book.koplugin-v0.0.8.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.0.7`：

#### 新功能

- :sparkles: (lockscreen): 使用 RGB 画布保留原始颜色 (c40628b)
- :sparkles: (plugin): 添加 KOReader 最低版本检查 (8dc3866)
- :sparkles: (copymanga): 支持已缓存章节直接打开 (8a8f305)
- :sparkles: (settings): 添加拷贝漫画配置支持 (7ae35f7)
- :sparkles: (book): 支持单书缓存清理与在线源同步删除 (3b4368f)
- :sparkles: (db): 已读标记同步进度至 100% (ab4e6ca)
- :sparkles: (copymanga): 添加后续章节后台预取 (251faa8)
- :sparkles: (copymanga): 添加后续章节后台预取 (3154f8a)
- :sparkles: (copymanga): 新增拷贝漫画数据源 (79642cb)
- :sparkles: (update): 展示月读更新日志并拆分安装流程 (e497af9)
- :sparkles: (store): 新增本地下载状态判断 (c27cecf)
- :sparkles: (catalog): 补充目录项的 path 字段 (12cfc3a)
- :sparkles: (update): 增加月读更新下载进度条 (4a747c8)

#### 修复

- :bug: (http): 修正连接状态探测逻辑 (6a30102)
- :bug: (lockscreen): 修正统计缓存并支持章节数 (b66ddac)
- :bug: (ui): 修正设置页分页高度计算 (c3c9200)
- :bug: (http): 避免离线时发起 HTTP 请求 (6ed9756)
- :bug: 修复失败 URL 缓存与离线连接失败处理 (f0f2497)
- :bug: (ui): 限制阅读器栏刷新区域 (7584742)
- :bug: (source): 限制缓存与待处理队列大小 (ac09eb3)
- :bug: (http): 修复 Turbo 连接失败导致离线崩溃 (c1529ce)
- :bug: (progress): 移除云端进度拉取失败弹窗 (aa98d62)
- :bug: (ui): 修正分页时当前页内容判断 (d03743b)
- :bug: (page_turn_animation): 修复日志模块引用 (57b40da)
- :bug: (page_turn_animation): 修复日志模块引用 (9566137)
- :bug: (reader_prefs): 修复插件字体冷启动回退默认字体 (8ad61c9)

#### 界面

- :lipstick: (copymanga): 将账户图标改为 account_circle (b09f8cb)
- :lipstick: (ui): 重构封面状态叠层并新增已读与下载标记 (1abb5af)

#### 重构

- :recycle: (ui): 重构图片解码为单任务后台队列 (fce986a)

#### 变更

- :white_check_mark: (tests): 为 reader bars 测试添加 ui/geometry 桩模块 (b4d033e)
- :white_check_mark: (tests): 添加拷贝漫画离线打开测试 (02a66fc)
- :white_check_mark: (tests): 重置网络管理模块缓存 (ad4280b)
- :white_check_mark: (tests): 重置网络管理模块缓存 (0ec8bd6)
- :globe_with_meridians: (l10n): 添加版本提示与未知版本翻译 (643b565)
- :white_check_mark: (tests): 增加拷贝漫画进度与目录缓存测试 (0802d98)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.0.7...v0.0.8
