# v1.0.6-beta.2

## 更新日志
- 页眉页脚：修复点击页眉页脚内部子菜单时崩溃的问题
- 图标选择器：优化搜素逻辑并重构，修复安卓端打开图标选择器时崩溃的问题
- 图标选择器：添加标签显示/隐藏切换按钮（右上角）
- 底部栏： 修复安卓端旋转屏幕后底部栏丢失的问题
## What's Changed
- Header & Footer: fix crash when tapping an item inside the menu
- Icon picker: optimize search logic and rework showIconPicker to fix crashes on Android
- Icon picker: add label toggle (eye / eye-off) to show or hide icon names in the grid
- Bottom bar: fix missing bottom bar after screen rotation on Android

# v1.0.6-beta.1

## What's Changed

- Fix crash when tapping an item inside the Header & Footer menu

# v1.0.5-beta.3

# What's Changed
- fix: prevent layout corruption when rotating screen
- Added bottombar to history/collections/coll_list

## 更新日志
- 修复旋转屏幕时布局混乱的问题
- 给历史记录/收藏/书单界面添加底部栏

# v1.0.5-beta.2

## What's Changed

- Added bottombar to history/collections/coll_list

# v1.0.4-beta.18

## What's Changed

- Fix crash when removing last bottom bar tab (empty tab list handling)
- Fix residual touch handler when removing the rightmost bottom bar tab
- Fix Deselect All not showing when bottom bar tab count reaches max limit
- Move Remove button next to Save in built-in action edit dialog
- Adjust title and author font size in list view
- Fix placeholder cover dim effect not showing when selected in filemanager
- Add 'Hide in PDF' option for bottom bar
- Improve Chinese translations
