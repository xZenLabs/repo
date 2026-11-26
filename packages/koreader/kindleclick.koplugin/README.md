# Bluetooth and Kindle Click controller for KOReader

A KOReader plugin for **Kindle** that controls the built-in Bluetooth and the official **Kindle Click** page-turner remote: pair it once in Kindle's native settings, then connect and reconnect after wake, rescue a frozen native Bluetooth stack, and view its state in KOReader's footer, Bookends, or a ZenOS Home widget.

[English](#english) | [中文](#中文)

---

## English

### Features

- **Rescues a frozen Bluetooth stack** — when Kindle's native Bluetooth wedges after sleep (state reads 0 and LIPC requests are accepted but no longer reach the controller), a one-tap transport rebuild brings the Click back in about 40 seconds. The plugin offers it automatically after a failed wake and never restarts services on its own.
- **One icon, three states** — Bluetooth off, Bluetooth on, and Click connected share a single footer slot. A matching icon font is bundled, and each state can also use any Unicode codepoint.
- **Wake recovery that stays out of the way** — after sleep the plugin lets the native stack settle, sends at most one enable request, then watches read-only for up to 30 minutes. It never restarts Bluetooth services on its own.
- **Page-turn mappings** for the Click on touch-only Kindles, without enabling full keyboard input.
- **Works with what you already use** — stock KOReader footer, Bookends, and a ZenOS Home widget with a tap-to-open quick menu.
- **Gesture actions** — toggle Bluetooth or connect the Click from KOReader's gesture manager.
- **Diagnostics and manual update check** built into the menu.

### Install

1. Pair the Click in Kindle's native Bluetooth settings first; the plugin has no pairing UI.
2. Copy the `kindleclick.koplugin` folder to:

   ```text
   /mnt/us/koreader/plugins/kindleclick.koplugin
   ```

3. Restart KOReader completely.
4. Open **Kindle Click** from the top menu.

When upgrading, delete the old folder first, copy the new one, then restart KOReader.

### Status display

| Where | How to enable |
|---|---|
| KOReader footer | **Kindle Click → Status icons (three states)** |
| Bookends | Add `%plugin_content{kindleclick}` to a Bookends line |
| ZenOS Home | Enable the **Kindle Click** widget under **Zen Settings → Home → Widgets** |

The plugin menu is under **Settings → Network → Kindle Click** and contains the Bluetooth switch, connection status, gestures, diagnostics, and update check.

### Rescuing a frozen Bluetooth stack

After a long sleep, Kindle's native Bluetooth occasionally freezes: `BTstate` reads 0, every LIPC request is accepted, but nobody holds `/dev/stpbt`, so nothing reaches the controller. This is a native WMT transport problem, not a plugin bug — plain enable requests cannot fix it.

The plugin offers two ways out:

- **Automatic offer** — if Bluetooth is still off about 45 seconds after wake and the `wmt_cdev_bt` reference count is 0, a dialog asks whether to rebuild the transport.
- **Manual** — **Kindle Click → Rebuild Bluetooth transport (experimental)** stops `acsbtfd`, `btmanagerd`, and `wmt_service`, confirms the reference count has dropped to 0, then starts them in reverse order. It takes about 40 seconds and the Click reconnects automatically.

The rebuild does not touch airplane mode or Wi-Fi preferences (Wi-Fi shares the transport and may blink briefly). In testing, all four wedges recorded on 2026-11-15 were recovered this way.

### Compatibility and limits

- Kindle only, tested on **KPW6 with firmware 5.20.1**; requires a jailbroken device with KOReader.
- Uses Kindle's native Bluetooth stack via LIPC — no extra daemon, no KHP, no input grabbing.
- The Click's brightness buttons are handled directly by Kindle's native system, so KOReader's own brightness UI does not follow them.
- Detection uses the real HID node (`VID:PID 0171:0443`); the native `kindle-input-pt` device does not mean a Click is connected.

### Screenshots

**Menu and Bluetooth controls**

![Kindle Click menu and Bluetooth controls](screenshots/menu.png)

**Three connection states sharing one icon position**

![Three connection states sharing one icon position](screenshots/status-icons.png)

**Status displayed by Bookends**

![Kindle Click status displayed by Bookends](screenshots/bookends.png)

### Documentation

- [Architecture and behavior](docs/architecture.md)
- [Troubleshooting and diagnostics](docs/troubleshooting.md)

### License

MIT

---

## 中文

一个只面向 **Kindle** 的 KOReader 插件：控制原生蓝牙、连接官方 **Kindle Click** 翻页器（包括伪装成官方 Kindle Click 的其他翻页器）、在系统蓝牙假死时一键救回，并在 KOReader 状态栏、Bookends 或 ZenOS 主屏显示当前状态。

### 功能

- **系统蓝牙假死救回**：长时间休眠后，Kindle 原生蓝牙偶发假死——`BTstate` 读到 0，LIPC 请求都被接受，但没人持有 `/dev/stpbt`，命令到不了控制器。插件可一键重建蓝牙传输层，约 40 秒后 Click 自动连回；唤醒恢复失败时会自动弹窗询问，但绝不会擅自重启蓝牙服务。
- **一个图标位、三种状态**：蓝牙关闭、蓝牙已开启、Click 已连接。自带配套图标字体，每种状态也可改用任意 Unicode 码位。
- **唤醒恢复不添乱**：唤醒后先等原生蓝牙栈稳定，最多只发送一次开启请求，然后只读观察最多 30 分钟；不会自动重启任何蓝牙服务。
- **翻页键映射**：为触屏版 Kindle 补上 Click 的翻页键，不启用整套键盘输入。
- **兼容现有显示方式**：KOReader 自带状态栏、Bookends、以及带快捷菜单的 ZenOS 主屏小组件。
- **手势动作**：可在 KOReader 手势管理中绑定「开关蓝牙」「连接 Click」。
- **菜单内置诊断信息与手动检查更新**。

### 安装

1. 先在 Kindle 原生蓝牙设置里完成 Click 配对；插件不提供扫描/配对界面。
2. 把 `kindleclick.koplugin` 文件夹复制到：

   ```text
   /mnt/us/koreader/plugins/kindleclick.koplugin
   ```

3. 完全退出并重新启动 KOReader。
4. 从顶部菜单打开 **Kindle Click**。

升级时先删除旧文件夹，再复制新文件夹并重启 KOReader。

### 状态显示

| 位置 | 开启方式 |
|---|---|
| KOReader 状态栏 | **Kindle Click → 状态栏图标（三种状态）** |
| Bookends | 在 Bookends 任意一行加入 `%plugin_content{kindleclick}` |
| ZenOS 主屏 | 在 **Zen Settings → Home → Widgets** 打开 **Kindle Click** 小组件 |

插件菜单位于 **设置 → 网络 → Kindle Click**，内含蓝牙开关、连接状态、手势、诊断与检查更新。

### 蓝牙假死救回

长时间休眠后，Kindle 原生蓝牙偶尔会假死：`BTstate` 读到 0，所有 LIPC 请求都返回 accepted，但 `/dev/stpbt` 无人持有，命令根本到不了控制器。这是原生 WMT 传输层的问题，不是插件本身的错误，单纯发开启请求救不回来。

插件提供两条路径：

- **自动提示**：唤醒约 45 秒后仍读不到蓝牙、且 `wmt_cdev_bt` 引用计数为 0 时，弹窗询问是否重建传输层。
- **手动**：**Kindle Click → 重建蓝牙传输层（实验）**。依次停止 `acsbtfd`、`btmanagerd`、`wmt_service`，确认引用计数归零，再按相反顺序启动，强制 STP 传输层重新初始化。约 40 秒完成，之后 Click 会自动连回。

重建不会改动飞行模式或 Wi-Fi 偏好（Wi-Fi 与蓝牙共用 WMT，可能短暂闪断）。2026-11-15 记录的 4 次假死均通过该功能恢复。

### 兼容性与限制

- 仅支持 Kindle，已在 **KPW6 / 固件 5.20.1** 上验证；需要越狱并安装 KOReader。
- 通过 LIPC 使用 Kindle 原生蓝牙栈，不需要额外守护进程、KHP，也不抢占输入设备。
- Click 的亮度键由 Kindle 原生系统直接处理，KOReader 自己的亮度界面不会跟随。
- 连接识别基于真实 HID 节点（`VID:PID 0171:0443`）；原生的 `kindle-input-pt` 存在并不代表 Click 已连接。

### 文档

- [实现与行为说明](docs/architecture.md)
- [故障排查与诊断](docs/troubleshooting.md)

截图见上方英文部分的菜单、三态图标与 Bookends 示例。

### 许可证

MIT
