# v1.0.7-beta.4

## What's Changed

- Vertical Bar: Add vertical bar-draggable pop-up launcher with pagination, labels toggle, and e-ink open/close animation (long-press to edit buttons / open the side bar settings menu)
- Add Dispatcher action: toggle bottom bar in reader
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Quick Actions: add built-in actions for SimpleUI library browse modes (Authors / Series / Tags)
- Quick Actions: improve the font list in both Font List and UI Font Switcher (font preview + recently-selected sorting)
- Panel: warmth slider now matches frontlight (ON/OFF button, scaled value labels, instant refresh for 'Show Slider Value'), fix accidental touch issue
- i18n: improve Chinese translation

# v1.0.7-beta.3

## What's Changed

- Vertical Bar: Add vertical bar-draggable pop-up launcher with pagination, labels toggle, and e-ink open/close animation (long-press to edit buttons / open the side bar settings menu)
- Add Dispatcher action: toggle bottom bar in reader
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Quick Actions: add built-in actions for SimpleUI library browse modes (Authors / Series / Tags)
- Panel: warmth slider now matches frontlight (ON/OFF button, scaled value labels, instant refresh for 'Show Slider Value'), fix accidental touch issue
- i18n: improve Chinese translation
<img width="1072" height="1448" alt="侧边栏-灰色" src="https://github.com/user-attachments/assets/a10119fc-6227-44f3-841c-166a10f180d9" />
<img width="1072" height="1448" alt="侧边栏-透明" src="https://github.com/user-attachments/assets/0d102068-51a7-44f3-aaa3-3aa8d727e8e5" />
<img width="1072" height="1448" alt="侧边栏－白色" src="https://github.com/user-attachments/assets/8ad97683-a992-489f-85dc-b58d90a4cb56" />

# v1.0.7-beta.2

## What's Changed

- Add Dispatcher action: toggle bottom bar in reader
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Quick Actions: add built-in actions for SimpleUI library browse modes (Authors / Series / Tags)
- Panel: warmth slider now matches frontlight (ON/OFF button, scaled value labels, instant refresh for 'Show Slider Value')
- i18n: improve Chinese translation

# v1.0.7-beta.1

## What's Changed

- Add Dispatcher action: toggle bottom bar in reader
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)

# v1.0.6-beta.11

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
