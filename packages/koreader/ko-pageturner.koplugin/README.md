# 翻页器 pageturner.koplugin

KOReader 的蓝牙翻页器插件（Kindle / Kobo），外加一个「想法选择器」：用翻页器直接选中并打开当前页的想法（他人段评和自己带笔记的划线），不用碰屏幕。

A Bluetooth page-turner plugin for KOReader (Kindle / Kobo), plus a picker that lets the pager select and open the thoughts (others' reviews and your own notes) on the current page.

## 功能

- **接管翻页器**：自己找到翻页器的输入设备并接进 KOReader，热插拔、设备重建后自动重新接管（cheap 轮询 + 月读蓝牙状态变化；断连后短退避重试，摸屏可立刻再连），不需要 externalkeyboard。
- **自定义手势**：下一个 / 上一个 / 确认各自单独录一个手势（某个键的单击、连按 2~3 下、长按），单键、双键、三键翻页器都能用。
- **想法选择器**：确认进入选择模式，当前页的段评和带笔记的划线依次高亮，再确认打开，弹窗里可滚动。
- **联动月读**：月读里开蓝牙就接管翻页器、自动连上；使用翻页器时不自动息屏（本会话连上过就闩住，Click 空闲断 BLE 不松手；只挡 AutoSuspend，不写 preventScreenSaver）；休眠唤醒后立刻重连；设置页在月读里，支持自动/手动检查更新（月读 UI）。没装月读也能正常使用（无自更新）。
- **多语言**：简体中文、繁体中文、English，跟随 KOReader 语言。

## 前置条件

- Kindle 或 Kobo 上的 KOReader。插件只负责接管输入设备，蓝牙连接本身有三种来源，对应[月读](https://github.com/AnkioTomas/moon)支持的三种蓝牙方案，任选其一：
  - Kindle：[kindle-hid-passthrough](https://github.com/zampierilucas/kindle-hid-passthrough) 守护进程（装在 `/mnt/us/kindle_hid_passthrough`，把蓝牙翻页器变成虚拟键盘 `/dev/input/eventX`）。没装月读时插件启动会拉起 `main.bin --daemon`，装了月读则由月读的蓝牙开关拉起。
  - Kindle 自带蓝牙（btfd）：没有 KHP 时，插件会停掉系统的 `input_manager`（它独占翻页器输入节点），退出 KOReader 时恢复。需要月读负责配对连接。
  - Kobo 自带蓝牙：由月读配对连接，插件接管生成的输入设备。**Kobo 路径没有在真机上验证过。**
- 想法选择器里的段评来自[月读](https://github.com/AnkioTomas/moon)；没装月读时只有自己带笔记的划线可选。

## 安装

把整个 `pageturner.koplugin` 目录复制到 KOReader 的 `plugins/` 下（Kindle 上是 `/mnt/us/koreader/plugins/`），重启 KOReader。

## 使用

1. 菜单：齿轮 → 网络 → **翻页器**，里面有「下一个 / 上一个 / 确认」三项，点哪项就为哪个动作录手势。
2. 点一项后在翻页器上做一个手势，做完稍等，立即生效。同一个手势不能绑给两个动作，随时可以单独重录某一项。
3. 例子：
   - 三键：三个键各单击。
   - 双键：两个键各单击，确认录成某个键连按两下。
   - 单键：单击=下一个，双击=上一个，三击=确认。

> 同一个键上绑了连按时，单击要多等约 0.4 秒才能确认不是连按。
> 长按只在翻页器按住期间真的不松开时才有；不少翻页器按下和松开是同时发的，录不到长按，请改用连按。

### 选择模式

| 动作 | 正常读书 | 选择模式 | 弹窗里 |
| --- | --- | --- | --- |
| 下一个 / 上一个 | 翻页 | 选下一条 / 上一条 | 滚动内容 |
| 确认 | 进入选择模式 | 打开选中项 | 关闭弹窗并回到读书 |

翻页或跳转会自动退出选择模式。

### 菜单

装了月读时，同样的入口也在月读设置 → 系统 → 本机 → 翻页器 页里。

- **清除全部按键绑定**：回到未绑定状态，之后重新录。
- **使用翻页器时不息屏 / 蓝牙开了自动连翻页器**：两个开关，默认开。不息屏跟「本蓝牙会话连上过」走，不跟瞬时连接态绑死。

## 排错

- **按一下翻两页**：翻页器自带键位预设（出厂就发 PgUp/PgDn 这类标准翻页键）时，一次按下会同时走两条路：一路由插件绑定的手势翻页，另一路由 KOReader 原生翻页键翻页。插件已在按键入口兜底：翻过一页后的 0.3 秒内，再来的按下（不管什么键码）一律不再翻页。仍双翻的话，把日志发来看看。
- 按键没反应：翻页器空闲几分钟常会自己断蓝牙，摸一下屏幕或按一下翻页器，插件会立刻重连并接管；还不行就看日志。
- 日志在 `/mnt/us/koreader/crash.log`，搜 `[pageturner`。

## 文件

| 文件 | 作用 |
| --- | --- |
| `pageturner_binds.lua` | 三个动作与手势显示名（主程序与月读设置页共用） |
| `main.lua` | 手势识别与绑定、选择模式、菜单、生命周期 |
| `pageturner_input.lua` | 找到并打开翻页器的输入设备，交给 KOReader（Kindle 无 KHP 时释放系统 input_manager） |
| `pageturner_moon.lua` | 联动月读的蓝牙开关，使用翻页器时不息屏（会话闩） |
| `pageturner_thoughts.lua` | 收集当前页可选的想法（段评 / 带笔记的划线） |
| `pageturner_l10n.lua` | 界面翻译 |
| `moon_source.lua` | 在月读里登记扩展 id `ext.pageturner` |

模块名都带 `pageturner_` 前缀：`require("input")` 这类名字会撞上 KOReader 自带模块。
