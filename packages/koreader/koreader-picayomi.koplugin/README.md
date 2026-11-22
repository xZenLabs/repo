# PicaYomi

[English](README.en.md)

面向 Kindle 等设备的 [KOReader](https://github.com/koreader/koreader) 漫画与小说阅读插件。支持多源搜索、在线阅读、章节下载、收藏和阅读历史，可调整漫画图像增强、条漫版式与墨水屏刷新。

[下载安装包](https://github.com/UFOAlastor/koreader_PicaYomi/releases/latest) · [漫画与小说源](https://github.com/UFOAlastor/PicaYomi_Sources) · [问题反馈](https://github.com/UFOAlastor/koreader_PicaYomi/issues)

## 页面预览

| 主页 | 详情页 | 漫画阅读 | 小说阅读 |
|---|---|---|---|
| ![主页](docs/screenshots/home.png) | ![详情页](docs/screenshots/detail.png) | ![漫画阅读](docs/screenshots/comic-reader.png) | ![小说阅读](docs/screenshots/novel-reader.png) |

## 安装

设备需已安装并能正常运行 KOReader。

1. 从 [Releases](https://github.com/UFOAlastor/koreader_PicaYomi/releases/latest) 下载 **`picayomi.koplugin-<版本>.zip`** 附件。
2. 退出 KOReader，将设备通过 USB 连接电脑。解压后，把 **`picayomi.koplugin`** 文件夹放入设备的 **`koreader/plugins/`**，最终应能找到 `koreader/plugins/picayomi.koplugin/main.lua`。
3. 安全弹出设备，启动 KOReader，点击屏幕顶部打开菜单，选择 **扳手与螺丝刀图标（工具）→ Picayomi**。

下载时选择插件 ZIP 附件；GitHub 的 “Source code” 压缩包不用于安装。更新已有安装前，请先备份旧插件和重要数据。

<img src="docs/screenshots/koreader-tools.png" alt="KOReader 工具菜单中的 Picayomi 入口" width="360">

### 让 Agent 帮你安装

将设备通过 USB 连接电脑，并允许一个能访问本机文件、下载文件的 Agent 执行下面的提示词。Agent 可协助完成电脑端安装；设备上的退出、弹出后启动和菜单检查仍需你配合。

```text
请帮我在已通过 USB 连接电脑的设备上安装 PicaYomi。
官方仓库：https://github.com/UFOAlastor/koreader_PicaYomi
安装包：https://github.com/UFOAlastor/koreader_PicaYomi/releases/latest

请直接完成可安全执行的检查、下载、备份和安装：
1. 识别已挂载的设备及其 KOReader 目录；确认 KOReader 已安装且已退出。
   找不到设备、发现多个候选或无法确定目标时，先问我，不要猜路径。
   若尚未安装 KOReader，说明前置条件后暂停，不进行越狱或修改固件。
2. 阅读官方安装与兼容说明，从正式 Release 下载匹配的
   picayomi.koplugin-<版本>.zip 附件，不使用 Source code 压缩包。
   校验官方提供的 SHA256 摘要；校验失败或兼容性无法确定时停止。
3. 检查空间与写入权限，将现有插件及相关数据备份到电脑，告知备份位置。
   保留账号、设置、收藏、历史和下载；不上传设备文件或日志。
4. 在电脑临时目录解压并检查文件路径，再把 picayomi.koplugin 安装到
   设备的 koreader/plugins/。保留旧插件以便回滚，不在设备上嵌套多余目录。
5. 核对复制文件与安装包一致，并确认 main.lua、_meta.lua 位于插件根目录。
   报告安装版本、目标路径、备份位置及任何未完成检查。
6. 提醒我安全弹出设备并正常启动 KOReader，在“工具 → Picayomi”检查入口。
   文件复制完成只代表安装文件就绪，实际启动由我确认。
不要强制重启设备、删除阅读数据或修改其他插件。
```

## 第一次使用

1. **安装内容源**：首次进入时选择 **安装**，通过内置订阅获取漫画和小说源，完成后重启 KOReader；选择 **稍后** 后也可在 **设置 → 源管理 → 更新源（全部订阅）** 安装。可用源与账号要求见[源仓库](https://github.com/UFOAlastor/PicaYomi_Sources)。
2. **选择作品**：在主页切换漫画或小说源，按需登录，再搜索或浏览。搜索可选择当前源或全部同类型源。
3. **开始阅读**：列表中点封面可放大，再点屏幕任意位置关闭；点标题进入详情。详情页的“开始”从头阅读，“继续”恢复进度；主页收藏、历史和已下载的封面可直接续读。退出阅读回到详情，再返回原页面。
4. **离线保存**：在详情页选择“下载章节”，完成后从主页“已下载”打开。在线缓存可能被清理，需要离线保留的章节请主动下载。

## 阅读与常用设置

- **多源浏览与搜索**：漫画、小说分组切换，支持推荐、最新、分类与排行等入口，具体取决于源能力。可搜索当前源或全部同类型源，结果标明来源；超时保留已取得的结果，未完成来源可重试，并保存搜索历史。
- **漫画在线阅读**：当前页按需加载，无需等整章下载完成；支持整页、条漫和横屏，详情页可设置单本版式。可提前加载后续图片，减少翻页等待。
- **漫画图像增强**：支持锐化、降噪＋锐化，以及加深或柔和对比度；小图可保边放大，开启预加载后尽可能提前准备下一页的增强效果。增强默认关闭，保留下载原图，也可能增加等待时间。
- **小说阅读**：正文与插图由 KOReader 排版，字体与排版沿用原生菜单；支持前后章切换、进度恢复和离线阅读。长按插图可查看大图并保存，固定文案过滤可在阅读或源设置中调整。
- **提前加载与自动下一章**：漫画可设提前加载 0～9 页，小说可设 0～5 章，0 表示关闭；默认分别为 3 页和 1 章。漫画与小说均支持自动下一章，在 **设置 → 阅读设置** 开启，默认关闭。
- **作品详情与章节目录**：查看简介、作者、分类、标签与阅读进度，点击长标题或简介可展开全文；目录优先显示缓存，点击“刷新信息”更新详情和章节，刷新失败保留已有内容。
- **章节下载与清理**：可选全部章节或未读章节，已下载内容不重复选择；删除下载时可选全部或已读，保留未读与未读完的章节。阅读时下载暂停，退出阅读后继续；断网保留任务，持续失败可手动重试，息屏下载可在设置中控制。
- **收藏与历史**：支持本地收藏、源站收藏和历史续读，主页封面可直接开始或继续阅读；源站收藏需对应账号与源支持。清理缓存保留账号、设置、收藏、历史和主动下载。
- **作品评论**：支持的源可查看评论全文与回复，具体取决于源能力及登录状态；不提供发表评论或章节吐槽。
- **手势与存储管理**：从屏幕边缘向内滑返回，列表中间左右滑动翻屏，边缘返回可调整或关闭。**设置 → 存储管理** 可查看漫画、小说的缓存和下载占用，并分别清理。

网络较慢或设备负担较重时，可降低提前加载数量；墨水屏有残影时可选完整刷新。修改漫画显示设置后，重新打开章节生效。

## 更新与卸载

在 **设置 → 关于 → 检查更新** 下载插件更新，完成后正常重启 KOReader。插件和源的自动检查默认开启，已有设置保持；确认更新时会一并安装订阅中的新增源，无需逐个选择。源更新也可在 **设置 → 源管理** 中操作。

手动更新时，退出 KOReader，备份后用新版替换 `plugins/picayomi.koplugin`，保留 KOReader 数据目录。卸载时仅移除该插件目录，已有阅读数据不会自动删除。版本变化与升级注意事项见 [Releases](https://github.com/UFOAlastor/koreader_PicaYomi/releases)。

## 帮助与限制

主要适配 Kindle，其他设备需实际验证。内容可用性、登录和下载权限由源站决定；Wi-Fi 已连接不代表源站可访问，大图也可能受设备内存限制。

遇到问题可先检查源版本、登录状态和网络，再重试。通过 [Issues](https://github.com/UFOAlastor/koreader_PicaYomi/issues) 反馈时，请提供设备型号、KOReader／插件／源版本、复现步骤和报错。需要时参考[诊断日志说明](docs/DEBUG.md)，分享前删除账号、会话和个人阅读内容。

## 许可证与使用说明

本项目采用 [MIT License](LICENSE)，组件许可见[第三方说明](THIRD_PARTY.md)。感谢 [PicaComic](https://github.com/Pacalini/PicaComic)、[rakuyomi](https://github.com/hanatsumi/rakuyomi) 和 KOReader 的设计参考。

本项目仅供学习与技术交流，不提供或托管漫画、小说内容。作品版权归相关权利人所有，请遵守当地法律与平台规则，支持正版，并自行承担使用责任。
