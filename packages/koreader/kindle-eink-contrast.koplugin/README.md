# Kindle E Ink Contrast for KOReader

[Tiếng Việt](README.vi.md)

[Download the installable KOReader plugin ZIP](https://github.com/mkdayyyy/kindle-eink-contrast/releases/download/v0.3.3-preview/kindle-eink-contrast-v0.3.3-preview-plugin.zip)

A KOReader plugin for Kindle screens where text looks very faint, as if a layer of fog were covering the page, and remnants of the previous page remain visible after turning it. That lingering text is called **E Ink ghosting**.

The plugin tells the display driver to use a lower temperature when refreshing the screen. That can select a different built-in waveform, the sequence of pulses that moves the E Ink particles. The goal is **darker text and fewer afterimages**.

**Observed on a Paperwhite 5:** At the default setting, text was very pale and traces from previous pages remained visible. At **10°C**, text looked darker and sharper, and the reader no longer saw ghosting during use. Page turns took longer and the screen flashed for longer. Results depend on the panel, firmware and temperature preset.

## Before and after on Kindle Paperwhite 5

Each pair shows the same view on the same device. The original photos are displayed at the same width, with slight differences in camera framing.

### Same book page

| Before | After enabling the plugin |
| :---: | :---: |
| <img src="docs/images/ppw5-reading-before.jpg" width="360" alt="Paperwhite 5 book page with faint menu text over the page"> | <img src="docs/images/ppw5-reading-after.jpg" width="360" alt="The same book page with darker text and less visible ghosting"> |

### Same KOReader menu

| Before | After enabling the plugin |
| :---: | :---: |
| <img src="docs/images/ppw5-menu-before.jpg" width="360" alt="KOReader menu on Paperwhite 5 with ghosted text from the book behind it"> | <img src="docs/images/ppw5-menu-after.jpg" width="360" alt="The same KOReader menu with much less text showing through"> |

## Install and use

1. Exit KOReader and extract the plugin ZIP linked above. Copy `kindle-eink-contrast.koplugin` to `koreader/plugins/` on the Kindle. If you installed an earlier preview, remove `kindle-eink-temperature.koplugin` or `ppw5einktemp.koplugin` before reopening KOReader.
2. Reopen KOReader, open a book and go to **Settings → Screen → Kindle E Ink Contrast**. The menu is in English.
3. Select a temperature to hold while reading (20°C, 15°C, 10°C, 5°C or 0°C). Turn a page and compare the contrast and any remaining ghosting against Auto. Select **Restore Auto** to return to the default.

The plugin restores Auto when you close a book or put the Kindle to sleep, then reapplies your choice when you resume reading in the same KOReader session. When you quit and reopen KOReader, select the preset again if you want to use it.

If KOReader stops responding or cannot restore Auto, restart the Kindle. To uninstall, exit KOReader and remove `kindle-eink-contrast.koplugin` from `koreader/plugins/`.

## Compatibility

| Models | Driver |
| --- | --- |
| Paperwhite 5, Paperwhite 5 Signature Edition, Paperwhite 6, Kindle Basic (2022 and 2024), Kindle Scribe (2022 and 2024) | MediaTek HWTCON or HWTCON v2 |
| Paperwhite 1–3, Voyage, Oasis 1, Kindle Basic (2014 and 2016) | NXP i.MX EPDC |
| Paperwhite 4, Oasis 2 and 3, Kindle Basic (2019) | NXP i.MX EPDC with the Zelda or Rex request layout |

The menu appears when the Kindle model, framebuffer driver name and request structure match. The contributor tested Scribe support on a 2024 model. If you report how it works on another device, include your Kindle model, firmware, KOReader version, and which preset you tried.

## How it works

On MediaTek Kindle models, the plugin sets the temperature through the HWTCON driver. While the override is active, the driver may also use it for refreshes requested by other processes. On NXP models, the plugin sets the temperature field in KOReader’s own refresh requests. **Show current setting** displays the driver’s reported temperature and waveform zone on MediaTek, or the value KOReader requests on NXP.

[Amazon’s published Kindle kernel sources](https://digprjsurvey.amazon.com/csad/help/node/200203720) · [KOReader Kindle model detection](https://github.com/koreader/koreader/blob/master/frontend/device/kindle/device.lua) · [KOReader framebuffer refresh paths](https://github.com/koreader/koreader-base/blob/master/ffi/framebuffer_mxcfb.lua)
