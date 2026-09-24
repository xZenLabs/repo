# v1.1.1

## 更新说明
> 修复一些已知问题
- 底部栏: 阅读界面由原来的直接替换原生footer改为与原生footer共存，上下排布（保持与Menu patch一致）
- 底部栏: 取消勾选“在阅读器中显示”时立即清除底栏触摸区域（避免误触）而非等到重排结束才彻底清除
- 底部栏:  仅当底栏高度发生变化时才重排，修复打开书籍时闪烁一下的问题
- 底部栏: 修复从阅读界面返回simpleui主屏幕后移除或添加底栏按钮无法立即更新的问题
- 页眉页脚: 修复缩略图生成失败的问题——渲染离屏缓冲区（缩略图、书籍地图、页面浏览器）时跳过页眉/页脚叠加
- 侧边栏: 删除无效的文件引用避免可能的崩溃

# v1.1.0

## 更新说明
> 添加侧边栏快捷菜单+阅读滑块+重构底部栏注入方式（寄生footer而非包裹widget）+更多内置动作
- 侧边栏: 增加侧边栏快捷菜单（竖滑翻页、横滑拖动，长按按钮-编辑，长按上翻页-设置，长按下翻页-动作池，无按钮数量限制)
- 快捷操作: 优化（阅读器、UI字体切换、页眉页脚）字体列表-字体预览、最近排序、选中最前
- 快捷操作: 添加阅读滑块（字号、间距、样式微调等）的内置动作/手势操作-长按滑块弹出滑块列表（勾选以添加至顶部面板）、长按右侧数值重置为默认、长按左边标签弹出阅读滑块或重置为默认
- 快捷操作: 添加更多流行插件的内置动作（到动作池中添加至顶部面板/底部栏/侧边栏）
- 快捷操作: 给依赖插件的内置动作做前置检查-不可用会在动作池列表显示为灰，全选添加会自动过滤排除，顶部面板/底部栏/侧边栏按钮自动过滤排除
- 快捷操作: 在顶部面板/底部栏/侧边栏彻底删除某动作时联动删除其他栏上的相同动作按钮（避免空引用）
- 顶部面板: 修复点击顶部弹出菜单时误触前光滑块、重构滑块菜单（长按滑块以添加更多阅读滑块至顶部面板）
- 顶部面板: 添加分页行（默认3行1页，行上按钮可快速切换按钮形状、显/隐标签、一页几行，可隐藏、可滑动翻页），移除最大66个的数量限制
- 底部栏：添加阅读器界面显示/隐藏底部栏的手势操作
- 底部栏：重构底部栏注入方式-由包裹 widget 改为寄生在Reader/Menu自身的footer里，修复进入阅读姐买你闪烁、进度错位的问题，彻底解决旋转、全屏切换等情形下底栏丢失及与simpleui重复包错位的问题（兼容性：可搭配本人仓库[simpleui v2.7.1-b](https://github.com/gytwo/simpleui.koplugin/releases/tag/v2.7.1-b)使用）
- 页眉页脚: 阅读界面显示底部栏时自动隐藏页脚
- 书库封面: 给进度为0%和100%的书籍也添加进度徽章
- 书库封面: 支持识别simpleui虚拟文件夹（作者/系列/标签）路径中的书籍图片从而正确绘制虚拟文件夹封面（封面网格&图片列表均适用）
- 书库封面：添加对内置依赖插件coverbrowser的前置检查，避免因coverbrowser未启用导致插件其他功能也无法使用。
- 其他: 完善中文翻译
<img width="1072" height="1448" alt="Screenshot_2026-09-23_214635" src="https://github.com/user-attachments/assets/89220b6c-bcba-4e11-99e1-d6f53ccf80bb" />
<img width="1072" height="1448" alt="Screenshot_2026-09-23_215002" src="https://github.com/user-attachments/assets/94c8906b-8a27-4466-8079-be01ed862920" />
<img width="1072" height="1448" alt="Screenshot_三体全集（全三册）_刘慈欣 epub_p582_2026-09-23_215332" src="https://github.com/user-attachments/assets/4dbcedbb-ebea-409c-9ea4-ab8edd8a23ba" />
<img width="1072" height="1448" alt="Screenshot_三体全集（全三册）_刘慈欣 epub_p579_2026-09-23_214042" src="https://github.com/user-attachments/assets/bab93817-3b26-4769-a650-01c5868116ab" />
<img width="1072" height="1448" alt="Screenshot_三体全集（全三册）_刘慈欣 epub_p582_2026-09-23_215342" src="https://github.com/user-attachments/assets/185d628a-eb76-4c65-92af-46cf9fade10b" />

# v1.0.6

## 更新说明
- 页眉页脚：修复点击页眉页脚内部子菜单时崩溃的问题
- 图标选择器：优化搜素逻辑并重构，修复安卓端打开图标选择器时崩溃的问题
- 图标选择器：添加标签显示/隐藏切换按钮（右上角）
- 快捷操作编辑框：添加新建/动作池按钮并重排按钮
- 快捷操作编辑框：添加/移除/排序后立即刷新面板
- 预设管理：添加“应用预设”至动作池列表（如无预设则回退至默认设置）
- 底部栏：修复安卓端旋转屏幕后底部栏丢失的问题
- 底部栏：修复从别的全屏界面进入历史记录/收藏界面时底部栏丢失的问题
- 底部栏：修复历史记录/收藏界面处理（添加/移动/排序等）按钮时崩溃的问题
- 底部栏：修复历史记录/收藏界面移除最右侧按钮时触摸区域残留的问题
- 底部栏：优化阅读界面底部栏显示/隐藏体验（阅读时修改设置立即生效，而不是翻页或重新打开书籍才生效）
- 兼容性：提升对[simpleui](https://github.com/gytwo/simpleui.koplugin/releases)主屏幕的兼容性（详情请查看readme或插件说明）
- 更新：修复检查更新偶尔崩溃的问题
## What's Changed
- Header & Footer: fix crash when tapping an item inside the menu
- Icon picker: optimize search logic and rework showIconPicker to fix crashes on Android
- Icon picker: add label toggle (eye / eye-off) to show or hide icon names in the grid
- Quick Actions editor: add 'New' and 'Action Pool' buttons to action edit dialogs
- Quick Actions editor: refresh panel and bottom bar immediately after add/remove/reorder
- Preset management: add 'Apply preset' to 'Action Pool' ( falls back to defaults if none)
- Bottom bar: fix missing bottom bar after screen rotation on Android
- Bottom bar: fix missing bottom bar when entering History/Collections from another fullscreen view
- Bottom bar: fix crash in History/Collections when handling tabs (add/move/sort/etc.)
- Bottom bar: fix touch zone residue after removing the rightmost tab in History/Collections
- Bottom bar: improve bottom bar show/hide experience in ReaderUI
- Compatibility: Improved compatibility with SimpleUI Homescreen (see README or Plugin Info for setup details)
- Updates: fix occasional crash when checking for updates
<img width="505" height="680" alt="simpleui主屏幕" src="https://github.com/user-attachments/assets/b720e94e-b711-474d-8d98-16f2c693ab5e" />
<img width="605" height="633" alt="image" src="https://github.com/user-attachments/assets/cff2a18b-0ff4-49b1-a2c3-ad4ccad6669c" />

# v1.0.5

## What's Changed
- Fix: prevent layout corruption when rotating screen
- Added bottombar to history/collections/favorites

## 更新日志
- 修复旋转屏幕时布局混乱的问题
- 给历史记录/书单/收藏界面添加底部栏

# v1.0.4

## What's Changed
- Fix crash when removing last bottom bar tab (empty tab list handling)
- Fix residual touch handler when removing the rightmost bottom bar tab
- Fix Deselect All not showing when bottom bar tab count reaches max limit
- Move Remove button next to Save in built-in action edit dialog
- Adjust title and author font size in list view
- Fix placeholder cover dim effect not showing when selected in filemanager
- Add 'Hide in PDF' option for bottom bar
- Improve Chinese translations
- 修复底部栏移除最后一个按钮时崩溃闪退的问题（无按钮时显示提示性文字）
- 修复底部栏移除最右边按钮后触摸区域仍为旧按钮的问题
- 修复底部栏因达数量限制而无法批量移除所有按钮的问题
- 将内置动作编辑框的移除按钮放至保存按钮左侧（保持与自定义动作编辑框相同布局）
- 调整显示模式列表视图下标题及作者字体大小（解决字体过大的问题）
- 修复无封面书籍的占位封面及列表视图下的书籍封面无选中效果的问题
- 添加在PDF中隐藏底部栏选项
- 完善中文翻译
