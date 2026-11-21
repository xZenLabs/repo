# FingerTips

A KOReader plugin that makes selecting text work more like it does on a phone. When you long-press and drag to highlight, your fingertip normally covers the words you're selecting. You can't even tell if you've selected the right words. And then when you let go, a pop-up with action options covers up your selection again. FingerTips solves both those problems.

- While you drag along a line, a **copy of that line floats just above your finger**, so you can see where the selection ends.
- **Handles** at both ends let you adjust the selection after you lift your finger.
- The selection **sticks to its line** while you slide sideways, so a small wobble doesn't jump to the line above or below.
- Sliding down a page, the end of the selection **stays just above your finger**, so your finger never covers it.
- KOReader's highlight popup is replaced by a **compact popup** that sits above the selection instead of on top of it, with the actions you choose.

| Without FingerTips | With FingerTips |
|:---:|:---:|
| ![Without FingerTips: a finger drags across a passage and hides the words being selected, then KOReader's popup appears on top of the highlight](images/without_fingertips.gif) | ![With FingerTips: the same passage, with a copy of the line showing above the finger while it drags, and a compact popup above the highlight after lifting](images/with_fingertips.gif) |

Without FingerTips, your finger hides what you're selecting, and then the popup covers your highlight. With FingerTips, you can see what you're selecting as you drag, and the popup stays clear of it.

## Tested on

Developed and tested on a **Kobo Clara BW** running **KOReader 2026.07.02**, with EPUB books.

Reports from other devices are welcome. This is an early version, and I have a feeling this one may not be smooth for everyone, so feedback of any kind is appreciated.

## Install or update

1. Download `fingertips.koplugin.zip` from the [Releases](../../releases) page and unzip it. You should have a folder named `fingertips.koplugin`.
2. Connect your e-reader to a computer with USB.
3. Copy into or replace the `fingertips.koplugin` folder in KOReader's `plugins` folder. On a Kobo that is `.adds/koreader/plugins/`. The `.adds` folder is hidden: on a Mac, press **Cmd+Shift+.** in Finder to show it.
4. Eject the device and restart KOReader.

To uninstall, delete the folder.

## Using it

### Selecting

Long-press a word and, without lifting, drag.

- **Along a line:** a copy of the line appears above your finger, grows a word at a time as you drag, and shows a little of the surrounding text in light grey. It goes away once your drag reaches another line.
- **Down the page:** a line is added to the selection once your finger is a little past it, so your finger stays below the selection and still doesn't cover it up. If you go too far, drag back up: lines come off again as your finger rises.
- **Up the page:** drag above the line you started on to extend the selection backwards.
- **Onto the next page:** in the bottom-right corner, KOReader's own selecting across pages still works.

A long-press on a single word without dragging still opens the dictionary, as usual.

### After you lift your finger

- A **compact popup** appears above the selection, or below it when there's no room. It has the same buttons as KOReader's own highlight popup, including buttons that other plugins add.
- It shows a few actions at a time. **More** shows the next set, and wraps around to the first set.
- **Drag either handle** to adjust the selection. The popup goes away while you adjust.
- **Tap elsewhere** to close the popup and drop the selection, as usual. **Long-press elsewhere** to start a new selection.

### Settings

Top menu → Tools tab (wrench icon) → FingerTips:

- **FingerTips on**: the main on/off switch. When it's off, selecting text works exactly as it does without the plugin.
- **Customize popup**: choose which actions appear and in what order.
  - **One row per set** shows 3 actions plus More; **Two rows per set** shows 7 plus More.
  - You can move your most-used actions to the first set for easy access. Tap an action to pick it, then use **Move up** and **Move down**. Tap its box to put it in the popup or take it out entirely.
  - The list is grouped the way the popup shows it: first set, second set, and so on. Actions you've taken off are listed last.

![The Customize popup screen: switching from two rows per set to one, then moving an action up](images/settings.gif)

## Where it works

Tested on the device while reading **EPUB** books. PDFs, comics and other fixed-layout documents haven't been tested yet.

## Credits

Written by David Friedman, working with [Claude](https://claude.com/claude-code), Anthropic's AI model.

## License

[AGPL-3.0](LICENSE), the same license as KOReader.
