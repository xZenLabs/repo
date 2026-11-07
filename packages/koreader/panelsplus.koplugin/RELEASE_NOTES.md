# v1.6.0 · 2026-11-07

<div align="center" style="margin-bottom: 15px">
  <img width="98%" height="auto" alt="moonlight-cover-release" src="https://github.com/user-attachments/assets/9f196d96-1805-400e-b082-c1f51403a854" />
  <em>Me greeting the moon. Small and beautiful moon...</em>
</div>

> "Moonlight is sculpture; sunlight is painting."
> -- **Nathaniel Hawthorne**, *The American Notebooks* (1838)

Welcome to another update, let's see what's new:

# Main Features
<div align="center">
  <table>
    <thead>
      <tr>
        <th width="50%" align="center">Feat 1: Dark mode Improved (Based on bug report from @Nabistay</th>
        <th width="50%" align="center">Feat 2: LiveLight Plugin Support</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/f3725241-478a-4a0e-9afa-7ef4b0affc6a" controls width="100%"></video>
        </td>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/19405e8a-a689-4c62-b89a-57713d915f91" controls width="100%"></video>
        </td>
      </tr>
      <tr>
        <td align="left" valign="top">
          <strong>Now you can invert dark colors for panels, and keep the rest of UI in dark mode.</strong> 
          <br></br>Tbh, this feature was already built-in in KOReader! but Panels+ was ignoring it (skill issue of mine)<br></br>I didn't know that until someone <a href="https://github.com/KristanLaimon/PanelsPlus/issues/15"> reported this bug</a> so I took the bug fix and I converted it into a feature. 
        </td>
        <td align="left" valign="top">
           A little QOL. Now LiveLight joins to Panels+ plugin's native support family. If you're interested, you can download it <a href="https://github.com/ironicsans/livelight.koplugin">here</a>. Neither it's paid advertising, nor I'm affiliated with the original author. I just found this plugin very useful for me and wanted to integrate it with Panels+.
        </td>
      </tr>
    </tbody>
  </table>
</div>

## Feat 3 | New official translation: Brazilian Portuguese <- Translated by @MatheusLope
<div align="center">
  <img width="80%" height="auto" alt="image" src="https://github.com/user-attachments/assets/8b23e029-15e3-4b3f-909c-61c1e3feb605" />
</div>



---
#### Releasing Schedule Change:
Starting with this version, I'll be releasing smaller updates more frequently. 🦊 

I've decided to make this change because keeping up with increasingly large updates for each new minor version, as I've done over the past four releases (v1.2.0, v1.3.0, v1.4.0, and v1.5.0), has become difficult to sustain.

It's not sustainable for me in the long run, and it also means that Panels+ receives updates less frequently...

I believe this is a win-win: you'll get updates faster, and I'll be able to keep developing Panels+ without burning myself out in the process.

And...

I planned v1.6.0 to be the manhwa update, but its getting more complicated to implement than I thought .... I plan to release it in v1.7.0 or v1.8.0

---
## Downloading

Panels+ has **two different builds/flavors**, choose the one that best fits your needs.

| | **Vanilla / Standard Build** | **OCR-Embedded Build** |
|:---|:---|:---|
| **Description** | The classic Panels+ experience, with all the improvements introduced in this update. | Everything from the standard build, plus **two specially fine-tuned OCR models** designed for manga lettering. |
| **Installation size** | Lightweight (~192KB) | Little larger, due to the included OCR models (~4.09MB) |
| **Native OCR** | ✅ Supported | ✅ Supported |
| **Included OCR models** | None (uses your existing KOReader Tesseract models) | ✅ English and Spanish, fine-tuned for manga lettering |
| **OCR accuracy** | Standard Tesseract recognition | Approximately **10–15% better accuracy** compared to generic Tesseract models for Spanish and English OCR models only. |
| **Custom OCR models** | ✅ Supported | ✅ Supported |
| **Default OCR language** | Depends on your installed models and configuration | English |
| **Switch OCR models** | ✅ Supported | ✅ Supported |
| **New features & QOL improvements** | ✅ All included | ✅ All included |
| **Download** | `panels_plus.koplugin.zip` | `panelsplus_with_ocrmodels.koplugin.zip` |

> **Which version should I choose?**
>
> Choose **Vanilla** if you prefer a lightweight installation and already have your preferred OCR models.
>
> Choose **OCR-Embedded** if you want the additional manga-optimized English and Spanish OCR models included out of the box.

Both versions are available in the **Assets / Downloads** section below.

# v1.5.1 · 2026-10-24

<p align="center">
<img width="95%" height="auto" alt="image" src="https://github.com/user-attachments/assets/e71d0930-f028-4949-b15e-99134e12a244" />
</p>

<div align="center">
  <table>
    <tbody>
      <tr>
        <td width="20%" align="center" valign="top">
<a href="https://github.com/user-attachments/assets/00a8d58c-fd3d-4006-82c2-4ecbdc7f183e">Comic in HD here.</a> 
        </td>
        <td width="40%" align="center" valign="top">
           Art made by: <a href="https://www.instagram.com/tomateranci0?exln=NGRtNXpieHZ3Ymo0">@tomateranci0 (Tumblr)</a> | <a href="https://www.tumblr.com/tomateranci0?source=share">@tomateranci0 (Instagram)</a> | <a href="https://madebyhuman.iamjarl.com"><img src="https://madebyhuman.iamjarl.com/badges/made-white.svg" alt="Made by Human" width="80" height="auto"></a>
        </td>
        <td width="40%" align="center" valign="top">
             Comic layout & dialogs: By me <a href="https://github.com/KristanLaimon">@KristanLaimon</a>
        </td>
      </tr>
    </tbody>
  </table>
</div>


Hello, **Panels+ users**. This update is mainly about taking OCR support to the next level and finally removing the **[Experimental]** tag.

Panels+ now features significantly improved, faster, and more reliable native OCR support. Whether you're reading a PDF with an embedded text layer or a manga made entirely of images, **Panels+ can now recognize text directly from the page.**

This release also brings a redesigned configuration menu, improved panel detection algorithms, new quality-of-life features, and several bug fixes. Let's get into what's new.

---

# Main Features

## 1. Significantly Improved OCR

<p align="center">
  <em>No PDF text layer required. Just images, and it works</em>
</p>

Panels+ can recognize words directly from images and send them to your dictionary for lookup, far better than before. **No preprocessing, no embedded text layer, and no extra steps required**

<div align="center">
  <table>
    <thead>
      <tr>
        <th width="50%" align="center">Native OCR — Images Only</th>
        <th width="50%" align="center">Force PDF Text Layer</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/f9c2908d-21ad-4fbd-a528-8db51af4ddc6" controls width="100%"></video>
        </td>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/7742d6a0-c2dd-4f9f-822c-c9b81871cf2c" controls width="100%"></video>
        </td>
      </tr>
      <tr>
        <td align="left" valign="top">
          <strong>Native OCR:</strong> Recognizes text directly from manga images with no embedded text layer.
        </td>
        <td align="left" valign="top">
          <strong>PDF text-layer option:</strong> Uses the PDF's existing text layer instead of native OCR (opt-in).
        </td>
      </tr>
    </tbody>
  </table>
</div>

These improvements applies for all supported formats: .CBZ, .CBR, .PDF, .EPUB, .MOBI, .KEPUB.

As long as you have the appropriate Tesseract language model installed in KOReader, you can use OCR with different languages

- **English:** For English manga and comics.
- **Spanish:** For Spanish-translated manga.
- **Other languages:** Depending on the Tesseract language models installed on your device.
- etc...

Simply select the appropriate OCR language model in the Panels+ configuration menu.

Panels+ includes OCR models fine-tuned for manga & comics, for English and Spanish (You can read more about this at the very end of these release notes):

Why only English and Spanish? you may ask. Those are the only languages I dominate myself so I can test the quality of those models natively. I don't feel confident to train italian, russian, chinese, etc -> models if I don't know how to read them in first place, probably they could be made with AI tools, but I don't like slop translations/lang related features. Despite that, I don't ignore the possibility to gradually add them in the future.

---

## 2. Redesigned Panels+ Configuration Menu

<p align="center">
  <img width="49%" alt="Panels+ Redesigned Configuration Menu - View 1" src="https://github.com/user-attachments/assets/717bf138-e21d-46a5-8f63-04bcb76f0379" /><img width="49%" height="auto" alt="image" src="https://github.com/user-attachments/assets/6bcae9e4-9358-41c0-801d-8955a6bd22a6" />

  <img width="99%" alt="Panels+ Redesigned Configuration Menu - View 2" src="https://github.com/user-attachments/assets/36aec568-6a5f-435f-adb3-9a8763f13c9a" />

</p>

With so many new configuration options introduced in this release, the old menu was starting to feel a little overcrowded.
To address this, I've **redesigned the Panels+ configuration interface** to make it cleaner, easier to navigate, and more comfortable to use (I hope so).

- **Improved navigation:** Less clutter and fewer unnecessary buttons.
- **Responsive interface:** Buttons automatically adjust their layout depending on whether your device is in portrait or landscape orientation.
- **Iconofied:** Added icons for settings in "More Config..." button.

The goal was simple: **more features without sacrificing usability.**

---

## 3. Improved Panel Detection Algorithms — Introducing `Smart(er)`

<div align="center">
  <table>
    <thead>
      <tr>
        <th width="50%" align="center">Safe mode (Default)</th>
        <th width="50%" align="center">Smart mode (Opt-in config)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/87c7670e-67ee-4bd2-bae7-856d0dc2c6ec" controls width="100%"></video>
        </td>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/4aac4f57-0d1e-4805-b466-f628b83ae81e" controls width="100%"></video>
        </td>
      </tr>
      <tr>
        <td align="left" valign="top">
          <strong>Safe Mode: Prioritizes stability</strong> <br></br> It's the previous version (v1.4.0) improved but kept the phylosophy to keep panels together if neccesary. <br></br>As you can see in the demo, it takes the entire panel as one single panel, it has sense since almost all the panels are connected by the main character in that page.
        </td>
        <td align="left" valign="top">
          <strong>Smart Mode: Prioritizes to find every panel possible</strong> <br></br> It's an alternative algorithm (an aggresive overhaul of Safe Mode) to find every panel, even those that are interconnected a little by a character or bubble dialog. <br></br>if the bubble dialog is really in the middle of 2 panels, it fallsback to Safe Mode behavior for that panel, thanks to this is capable to recognize panels that Safe mode prefer not to show you. <br></br> But, due to the aggresive nature of it, sometimes it could find false positives, some blank panels, but looks cool though. Optional to set. By default Panels+ uses Safe Mode. <br></br> As you can see in the demo, it finds all the panels taking into account that is a hard layout manga page.
        </td>
      </tr>
    </tbody>
  </table>
</div>


---

## 4. Smooth Transitions "ease" styles

<div align="center">
  <video
    src="https://github.com/user-attachments/assets/81d1e9e2-f607-4c24-8af1-6371b057a770"
    width="25%"
    controls>
  </video>
</div>

This is a small addition to Smooth transition. It looks way better on android + desktop/linux devices, not that great in e-ink based ones like Kindle, but still available. I took inspiration from CSS transitions values. In case you're frontend dev, I've added the CSS equivalent just to make clearer how it works.

| Style | Timing | Description | CSS equivalent |
| --- | --- | --- | --- |
| `linear` | Progress changes evenly throughout the transition. | Steady movement without deliberate acceleration or deceleration. | `linear` |
| `ease` **(default)** | Starts slowly, accelerates early, then slows down toward the destination. | A quick movement with a gentle landing; the acceleration and deceleration are not symmetrical. | `cubic-bezier(0.25, 0.1, 0.25, 1)` |
| `ease-in` | Starts slowly and accelerates toward the end. | Builds momentum as it approaches the next panel. | `cubic-bezier(0.42, 0, 1, 1)` |
| `ease-out` | Starts quickly and decelerates toward the end. | Responds quickly, then settles gently onto the next panel. | `cubic-bezier(0, 0, 0.58, 1)` |
| `ease-in-out` | Accelerates through the first half and decelerates through the second half. | A balanced slow start and slow finish, with faster movement in the middle. | `cubic-bezier(0.42, 0, 0.58, 1)` |
| **Classic** | Uses linear timing with the earlier fixed-zoom camera pan. | Slides between panels at the destination's zoom instead of gradually zooming in or out. | No direct CSS equivalent: Classic changes the rendering approach, not just the timing curve. |


---

## 5. Profile Settings

<div align="center">
  <video
    src="https://github.com/user-attachments/assets/d590f554-23ce-45e2-a19a-99577f40cd40"
    width="25%"
    controls>
  </video>
</div>

I realized there are combos of "settings" that worked better together specifically, but I needed to remember them every time i wanted to switch a group of settings. 

> Why not creating stored profile settings?. Create them, edit them, break them, or never use them. 

By default Panels+ includes some recommended Profiles by me, for e-readers and android/desktop. You'll see them the first time you download this update, otherwise, use the option: "Add defaults" to add them.You can found this option in the button "Profile Setting: ####" at the end of options. It's not in the video because I'm too lazy to update it just to add that new button in the showcase.

--- 

`Probably there are other little features related to those, but it will make this release too "texty". Discover them by your own!.` 

---

# Secondary Features & Quality-of-Life Improvements

## 1. New Two-Finger Tap Gesture | Made by @Pixxel123 

Panels+ now supports an alternative activation gesture: **double-finger tap**. Previously, the plugin relied on long-press interactions a l w a y s, which could conflict with gestures used by other KOReader plugins of yours.

With this new option, you can choose a different way to trigger Panels+ without interfering with your existing setup. Completely optional and configurable.

<div align="center">
  <table>
    <thead>
      <tr>
        <th width="50%" align="center">Demo (Recorded)</th>
        <th width="50%" align="center">How to configure it</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/46cfb6a1-3f66-48fc-a8eb-0ecc5a7a6921" controls width="100%"></video>
        </td>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/8b774ac0-1d66-46f5-8052-d5b99cf21e84" controls width="100%"></video>
        </td>
      </tr>
      <tr>
        <td align="left" valign="top">
            Testing it with two-fingers. Can't be made in desktop/android for obvious reasons, only clicks there.
        </td>
        <td align="left" valign="top">
          Configure path
        </td>
      </tr>
    </tbody>
  </table>
</div>

---


## 2 & 3. Auto-Rotate Double-Page Spreads & Remove Fold Lines | Made by @Pixxel123

Panels+ now supports **automatic rotation for double-page illustrations**, alongside a feature to remove those annoying black fold lines that some manga scans have in the middle. Added double-page spread automatic orientation, and return to your previous orientation when you move to a normal page. No need to manually rotate your device every time.

You can configure this behavior to work:
- **Off:** No automatic rotation.
- **Panel Viewer only:** Rotates double-page illustrations when using Panels+.
- **While reading:** Rotates your screen directly in KOReader's normal reading view.
- **Both:** Enables rotation in both cases.
- **Rotation direction**: clockwise, counter-clockwise, or follow KOReader's default orientation.

<div align="center">
  <img width="75%" alt="Double-page spread fold strip removal example" src="https://github.com/user-attachments/assets/61ef544c-b595-4b5d-9d4b-7415bf739563" />
  <p><em>Example of the black fold strip between two manga pages.</em></p>
</div>

This works directly while reading or inside Panels+ Panel Viewer. Fold removal is **enabled by default**, but you can disable it whenever you want.

**NOTE:** This feature works with double-page illustrations stored as a single wide page/image. It doesn't combine two separate physical pages into one illustration (yet). Also, if the original manga scan lost some artwork at the fold, removing the black strip obviously won't magically recover it.

All of these features are configurable from the Panels+ menu, under the rotation settings in "More Panel Viewer Settings".

> If you use [KCC](https://github.com/ciromattia/kcc) to pre-process your mangas/comics, this won't be an issue for you at all.

---

## 4. Better PDF Text-Layer OCR Support | Made by @MartinoAichner

He made the first OCR improvement which I based my following work until make the current OCR support today. OCR Recognition improved for PDF documents containing embedded text layers.
These changes help Panels+ handle text-based PDF content more reliably, improving the overall dictionary lookup experience.

<div align="center">
  <table>
    <thead>
      <tr>
        <th width="50%" align="center">Demonstration provided by @MartinoAichner</th>
        <th width="50%" align="center">How to configure it</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td width="50%" align="center" valign="top">
            <img width="800" alt="PDF Text-Layer OCR Improvements" src="https://github.com/user-attachments/assets/2a72596c-efb5-48bc-9d1c-caa8eb33b2d4" />
        </td>
        <td width="50%" align="center" valign="top">
          <video src="https://github.com/user-attachments/assets/a5d0da55-79d3-4c7e-8410-ce942f333aa4" controls width="100%"></video>
        </td>
      </tr>
      <tr>
        <td align="left" valign="top">
            Demo. What else can I say?
        </td>
        <td align="left" valign="top">
          Configure path
        </td>
      </tr>
    </tbody>
  </table>
</div>

---

## 5. Simplified Chinese Translation added | Translated by @IMJXXL

<img width="49%" alt="image" src="https://github.com/user-attachments/assets/0cad18fe-b526-4b03-a0f1-cfa44217d17f" /> <img width="49%" alt="image" src="https://github.com/user-attachments/assets/e34333a0-15f1-4cbb-8c7d-60881df1c1be" />
<em>You can access this by simply changing your KOReader language.</em>

And many overall bug fixes here and there.

# New Contributors

Thanks to everyone who made their first contribution to Panels+:

- **@Pixxel123** — Made their first contribution in [Pull Request #7](https://github.com/KristanLaimon/PanelsPlus/pull/7).
- **@MartinoAichner** — Made their first contribution in [Pull Request #9](https://github.com/KristanLaimon/PanelsPlus/pull/9).
- **@IMJXXL** — Contributed a **Simplified Chinese translation**.
- **@TomateRan**  — Artist who made the art cover for this release, also a developer sometimes.

---

## Panels+ downloading

Starting from now, Panels+ comes in **two different builds/flavors**, allowing you to choose the one that best fits your needs.

| | **Vanilla / Standard Build** | **OCR-Embedded Build** |
|:---|:---|:---|
| **Description** | The classic Panels+ experience, with all the improvements introduced in this update. | Everything from the standard build, plus **two specially fine-tuned OCR models** designed for manga lettering. |
| **Installation size** | Lightweight (~192KB) | Little larger, due to the included OCR models (~4.09MB) |
| **Native OCR** | ✅ Supported | ✅ Supported |
| **Included OCR models** | None (uses your existing KOReader Tesseract models) | ✅ English and Spanish, fine-tuned for manga lettering |
| **OCR accuracy** | Standard Tesseract recognition | Approximately **10–15% better accuracy** compared to generic Tesseract models for Spanish and English OCR models only. |
| **Custom OCR models** | ✅ Supported | ✅ Supported |
| **Default OCR language** | Depends on your installed models and configuration | English |
| **Switch OCR models** | ✅ Supported | ✅ Supported |
| **New features & QOL improvements** | ✅ All included | ✅ All included |
| **Download** | `panels_plus.koplugin.zip` | `panelsplus_with_ocrmodels.koplugin.zip` |

> **Which version should I choose?**
>
> Choose **Vanilla** if you prefer a lightweight installation and already have your preferred OCR models.
>
> Choose **OCR-Embedded** if you want the additional manga-optimized English and Spanish OCR models included out of the box.

Both versions are available in the **Assets / Downloads** section below.

**If you enjoy Panels+, consider giving the repository a ⭐ on GitHub. It helps more people discover this project.**

---

v1.5.1: This release patch fixes an error with OCR Model Selection, that, for some reason it wasn't recognizing your hand-installed teserract OCR models.

# v1.5.0 · 2026-10-18

<p align="center">
<img width="1566" height="237" alt="image" src="https://github.com/user-attachments/assets/0ea9d2b0-c6f6-41fc-9c17-6424c0753139" />
</p>

If you don't use any OCR related feature, you can download this release without any problems, otherwise...

Prefer the newer version, with bug fixes here: https://github.com/KristanLaimon/PanelsPlus/releases/tag/v1.5.1

# v1.4.0 · 2026-09-12

<img width="1578" height="840" alt="image" src="https://github.com/user-attachments/assets/a0765887-4b37-4169-8588-902db0aecd89" />

# Panels+ | The format-verse (& improved panels finding)

Built from tag: `v1.4.x`

Hi Panels+ users, this new update brings some of the biggest improvements to Panels+ yet, added support for more file formats, panels finding better accuracy, animations, added more customizable options, new navigation mode, translations/localizations, removed useless butttons and more.

This time I wanted to provide support for text-based formats like `.epub`, `.kepub` and `.mobi` & improve a lot the panels finding internal algorythm because I found many false panel positives and some broken panels and weird panel ordering in v1.3.0.

## Main Features

### (1) .MOBI, .EPUB, .KEPUB Officially supported (and any other format that includes embbeded images)

These 3 new formats are joining in to the family of Panels+ (Previously only: `.cbr`, `.cbz`, `.pdf`), due to popular demand from my reddit users.

https://github.com/user-attachments/assets/675111ac-779e-44a6-a209-b42c876c91af

### (2) Complete overhaul to internal panel finding algorythms

In v1.3.0, some users and myself, found weird panels ordering. Sometimes it could be from bottom to top?, other times it just skips panels!. So I've started to work on this, with better testing, and manually mapping over 1200+ panels by hand then comparing Panels+ to the previous hand-made panels. (Took a while to do)

https://github.com/user-attachments/assets/28a43edc-22e8-4d71-a236-5fb3b2a87815

#### Button "Smart | Quick | Deep" mode removed.

Originally I made these changes to the "deep mode" button, but it got so good (more performant and faster) than quick and smart mode, so there wasn´t any sense keeping the old ones. I removed the button, now is always "deep mode" but works better and for comics and mangas equally.

<img width="1881" height="413" alt="image" src="https://github.com/user-attachments/assets/51d3b7e9-b709-45f5-b621-339229c0790b" />

#### Benchmarks

I did some benchmarks:

<table>
  <thead>
    <tr>
      <th>Metric</th>
      <th align="center">Legacy (v1.3.0)</th>
      <th align="center">Now (v1.4.0)</th>
      <th align="center">Improvement</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Global Precision</td>
      <td align="center">78.2%</td>
      <td align="center">95.8%</td>
      <td align="center">+17.6%</td>
    </tr>
    <tr>
      <td>Global Recall</td>
      <td align="center">80.5%</td>
      <td align="center">93.8%</td>
      <td align="center">+13.3%</td>
    </tr>
    <tr>
      <td>Global F1 Score</td>
      <td align="center">79.4%</td>
      <td align="center">94.8%</td>
      <td align="center">+15.4%</td>
    </tr>
    <tr>
      <td>Average Matched IoU</td>
      <td align="center">0.89</td>
      <td align="center">0.95</td>
      <td align="center">+0.06</td>
    </tr>
    <tr>
      <td>Perfect Reading Order Pages</td>
      <td align="center">358 / 764 (46.9%)</td>
      <td align="center">626 / 764 (81.9%)</td>
      <td align="center">+35.0%</td>
    </tr>
  </tbody>
</table>

<h3>Per-manga dataset made by hand</h3>
Why these specific mangas/comic?, because they're my favorite and I had to use some files anyways. But these improvements affects any other comics/manga as well.

<table>
  <thead>
    <tr>
      <th>Volume</th>
      <th>Metric</th>
      <th align="center">Legacy (v1.3.0)</th>
      <th align="center">Now (v1.4.0)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Bloom Into You Vol. 8</td>
      <td>F1 / Precision / Recall</td>
      <td align="center">79.9% / 74.6% / 86.1%</td>
      <td align="center">93.4% / 96.8% / 90.2%</td>
    </tr>
    <tr>
      <td>Komi Can't Communicate Vol. 1</td>
      <td>F1 / Precision / Recall</td>
      <td align="center">87.6% / 89.8% / 85.5%</td>
      <td align="center">96.4% / 97.3% / 95.6%</td>
    </tr>
    <tr>
      <td>Miss Kobayashi's Dragon Maid Vol. 2</td>
      <td>F1 / Precision / Recall</td>
      <td align="center">66.2% / 70.2% / 62.6%</td>
      <td align="center">92.9% / 95.0% / 91.0%</td>
    </tr>
    <tr>
      <td>Scott Pilgrim Vol. 5</td>
      <td>F1 / Precision / Recall</td>
      <td align="center">80.4% / 77.2% / 83.8%</td>
      <td align="center">95.9% / 94.4% / 97.4%</td>
    </tr>
  </tbody>
</table>

## (3) New navigation mode. `Nav. Animated`
I realized e-ink devices have specific hardware for swiping and exclusive animation transitions (no surprise I guess) so, why not giving that to Panels+!? (This is only available in Kindle, Kobo, and supported e-ink devices, doesn´t work in Android and Desktop/Linux)

https://github.com/user-attachments/assets/091835ec-11c5-48a3-a22b-60d60e2700b0

## Secondary features
Not only the previous ones, I've added many other qualities of lifes features!
<div align="center">

<table>
<thead>
<tr>
<th align="center">Feature</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>

<tr>
<td align="center"><strong>Per-Document Settings Persistence</strong></td>
<td>
<strong>Remember preferred settings for every individual manga or comic</strong>
<br><br>
Panels+ now remembers your reading preferences on a per-book basis. You can read a Western comic in <strong>Comic mode</strong> with <strong>Margin crop</strong>, then switch to an action manga using <strong>Manga mode</strong>, <strong>Strict crop</strong>, and <strong>Animated navigation</strong>.
<br><br>
As soon as you reopen a title, Panels+ automatically restores its previous configuration, so you no longer need to reconfigure your preferred reading setup every time you switch between books.
</td>
</tr>

<tr>
<td align="center"><strong>Invert Tap &amp; Swipe Controls</strong></td>
<td>
<strong>Fine-grained customization for touch navigation and gesture flow</strong>
<br><br>
Default swipe gestures and tap zones now naturally mirror the selected reading direction: <strong>Manga mode</strong> advances to the right, while <strong>Comic mode</strong> advances to the left.
<br><br>
If you prefer the opposite behavior, the new <strong>Invert tap screen direction</strong> and <strong>Invert panel swipe direction</strong> options let you customize taps and gestures independently.
</td>
</tr>

<tr>
<td align="center"><strong>More Config... Menu</strong></td>
<td>
<strong>A dedicated place for advanced Panels+ configuration</strong>
<br><br>
Important Panels+ settings have been moved out of the main KOReader menu and consolidated under the new <strong>More Config...</strong> button, keeping the primary interface cleaner while making advanced options easier to find.
<br><br>
This menu includes configuration for <strong>per-document settings persistence</strong>, <strong>tap direction inversion</strong>, and <strong>panel swipe direction inversion</strong>.
<br><br>
<div align="center">
<video src="https://github.com/user-attachments/assets/9df75a2c-696e-4c73-8ac9-f67889a0b5ff" alt="Panels+ More Config menu" width="520">

</div>
</td>
</tr>

<tr>
<td align="center">
<strong>Keyboard Navigation</strong><br>
<code>A</code> / <code>D</code> &amp; Arrow Keys
</td>
<td>
<strong>Navigate panels using physical keyboards</strong>
<br><br>
Readers using devices with built-in hardware keyboards or paired Bluetooth keyboards can now navigate panels without reaching for the touchscreen.
<br><br>
Use <code>A</code> for the previous panel and <code>D</code> for the next panel, or use <code>ArrowLeft</code> and <code>ArrowRight</code>.
<br><br>
</td>
</tr>

<tr>
<td align="center"><strong>Device Rotation Zoom Retention</strong></td>
<td>
<strong>Maintain panel framing and zoom across screen rotation</strong>
<br><br>
Rotating the device while zoomed into an image or reflowable book now properly recalculates and preserves the current panel framing and zoom level.
<br><br>
Previously, rotating the screen could reset the zoom or allow KOReader's global document settings to overwrite the active Panels+ view.
<br><br>
</td>
</tr>

<tr>
<td align="center">
<strong>Spanish Translation</strong><br>
<code>i18n</code>
</td>
<td>
<strong>Full localization architecture with a hand-crafted Spanish translation</strong>
<br><br>
Panels+ is now fully localizable through a new <strong>internationalization (i18n)</strong> system.
<br><br>
Version 1.4.0 includes a complete Spanish translation covering viewer buttons, menus, dialogs, settings, and configuration descriptions. A contributor guide is also available for anyone interested in bringing Panels+ to additional languages.
<br><br>
<div align="center">
<img width="670" height="1042" alt="image" src="https://github.com/user-attachments/assets/b5c54d61-cf2f-4312-baf6-8d4ccd10f800" />
</div>
</td>
</tr>

<tr>
<td align="center"><strong>Package Manager Integration</strong></td>
<td>
<strong>One-click installation through KOReader package managers</strong>
<br><br>
Installing and updating Panels+ is now easier than ever. With a standardized <code>manifest.json</code> and stable release assets, Panels+ can now be discovered and installed through both the <strong>KOReader Plugin Appstore</strong> (<code>appstore.koplugin</code>) and the <strong>ZEN Package Manager</strong> (<code>zen_ui.koplugin</code>).
</td>
</tr>

</tbody>
</table>




</div>

## Fixes

- Fixed reading flow sequencing where panels in complex or irregular Western comic layouts were visited out of narrative order.
- Fixed stacked vertical panels in Manga mode causing erratic jumps instead of following top-to-bottom reading order within columns.
- Fixed device orientation being reset or overwritten by KOReader's global document configuration when changing orientation inside Panels+.
- Fixed panel zoom level not being restored properly when rotating the screen while reading embedded images in reflowable books.
- Fixed reversed swipe directions in Manga and Comic modes so that swipe gestures naturally align with reading flow (with an option to invert if preferred).
- Fixed "Smooth" navigation ignoring the "With margin" crop setting and losing panel margin during camera pans.
- Fixed smooth navigation options not being available for embedded images in reflowable formats (.epub, .mobi, .kepub).
- Fixed physical page-turn button navigation regressions on Kobo hardware and Bluetooth page-turner devices.
- Fixed sudden viewer close / crashes when a document was closed or modified by external plugins by adding safe-guards.
- Shortened and cleaned up verbose menu labels (e.g. `[Text Selection]: Touch & hold`).
- Fixed potential memory leaks and redundant page rasterizations when navigating across consecutive embedded images.
- Reduced CPU overhead and added reusable scratch buffers to keep panel detection snappy on low-RAM e-ink readers.

## Upgrading

Copy `panels_plus.koplugin` over your existing folder and restart KOReader. Your settings and reading progress are kept. All new navigation options (including Nav. Animated and inverted tap/swipe controls) can be configured directly from the panel viewer's "More config..." menu.

## Author

- KristanLaimon

---

Update: 13th October 2026 
## New Supported Language: `Chinese Simplified` thanks to @IMJXXL from ["PR"](https://github.com/KristanLaimon/PanelsPlus/issues/12)
<img width="40%" alt="image" src="https://github.com/user-attachments/assets/0cad18fe-b526-4b03-a0f1-cfa44217d17f" /> <img width="40%" alt="image" src="https://github.com/user-attachments/assets/e34333a0-15f1-4cbb-8c7d-60881df1c1be" />
<em>You can access this by simply changing your KOReader language.</em>
Available in `panelsplus_1-4-0-with-chinese-simplified.zip` release.

You can download any zip, both are Identical. The canonical zip is `panels_plus.koplugin.zip`, but kept `panels_plus-1.4.0.zip` for compatibility in ZenPM database's plugin metadata.

# v1.3.0 · 2026-08-20

<img width="100%" alt="Panels+ v1.3.0 banner" src="https://github.com/user-attachments/assets/658897e4-965f-4746-998e-226895e6697f" />

Built from tag: `v1.3.0`

Welcome to **The Touchy Update**! For this release, I focused on polishing several features I found myself missing while reading on my e-reader over the past few weeks. 

Why "The Touchy Update", you ask? Well, it introduces new **experimental OCR support** (activated via a long press on text). Ironically, it also brings **touchless functionality** to Kobo devices, allowing you to turn pages using physical buttons and compatible Bluetooth page-turners.

This update also includes quality-of-life improvements for rotation handling, dark mode support, and much more. Check out the details below:

## Highlights

<div align="center">

<table>
  <colgroup>
    <col style="width: 20%">
    <col style="width: 80%">
  </colgroup>
  <thead>
    <tr>
      <th align="center">Feature</th>
      <th align="left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><strong>Word Lookup</strong></td>
      <td>
        <strong>Touch &amp; hold to select text and look up words, even in comics/manga</strong><br><br>
        Long-press a word inside a zoomed-in panel to select it and open the dictionary, just like you would on any regular text page. This now works on comic and manga pages too, which normally have no selectable text at all! Works across CBZ, CBR, and PDF. <em>Note: This is still experimental. Word detection is tricky on hand-lettered or stylized comic text and might not always get it exactly right.</em><br><br>
        <div align="center">
          <video src="https://github.com/user-attachments/assets/1e08f664-c036-4b15-bedf-bc4c4cf5cc00" width="40%" controls muted autoplay loop playsinline></video>
          <br>
          <em>🎥 Long-pressing to select text and trigger the dictionary popup on a comic page.</em>
          <br>
          <strong>IMPORTANT:</strong> To use this feature, you'll need to set up a couple of things first:
          <ul>
            <li><em>Install an OCR engine in KOReader by <a href="https://koreader.rocks/user_guide/#L2-ocr">following the official KOReader guide</a>.</em></li>
            <li><em>Install at least one dictionary. You can do this by <a href="https://www.youtube.com/watch?v=fthGMdpUfR0">following this tutorial for manual installation</a>, or by using KOReader's built-in online dictionary installer.</em></li>
          </ul>
          <em>(Note: Step-by-step instructions for the built-in installer are outside the scope of these release notes.)</em>
        </div>
      </td>
    </tr>
    <tr>
      <td align="center"><strong>Dark Mode</strong></td>
      <td>
        <strong>Dark mode for the panel viewer</strong><br><br>
        The panel viewer now fully respects KOReader's night mode. Previously, switching to dark/night mode inverted the rest of the reader but left the panel viewer—panel art, borders, the bottom toolbar, everything—lit up bright white regardless.<br><br>
         <div align="center">
            <video src="https://github.com/user-attachments/assets/b0d8380c-e523-462c-a33e-21704fb79043" width="40%" controls muted autoplay loop playsinline></video>
            <br>
            <em>🎥 Switching to dark mode with the panel viewer seamlessly updating.</em>
        </div>
      </td>
    </tr>
    <tr>
      <td align="center"><strong>Edge Zoom</strong></td>
      <td>
        <strong>One-handed zoom with edge swipes</strong><br><br>
        Swipe up along the left edge of the screen to zoom into the current panel, and swipe down to zoom back out. No pinch gesture is needed, so you can easily zoom in and out one-handed while holding the device.<br><br>
        <div align="center">
          <video src="https://github.com/user-attachments/assets/09c51cf0-8748-4701-b198-9468db39c442" width="40%" controls muted autoplay loop playsinline></video>
          <br>
          <em>🎥 Swiping up and down along the screen edge to zoom in and out seamlessly.</em>
        </div>
      </td>
    </tr>
    <tr>
      <td align="center"><strong>Tap to Navigate</strong></td>
      <td>
        <strong>Tap the screen edges to move between panels</strong><br><br>
        A new toggle lets you tap the left or right edge of the screen to jump to the previous or next panel, instead of relying solely on swipes or on-screen buttons. Which side goes forward depends on whether you're reading comic-style or manga-style. Swipe navigation can also be turned off entirely if you prefer using only taps, buttons, or physical keys.<br><br>
        <div align="center">
          <video src="https://github.com/user-attachments/assets/c594bee5-a4c8-415a-a566-f87484d319a4" width="40%" controls muted autoplay loop playsinline></video>
          <br>
          <em>🎥 Tapping the screen edges to quickly jump between previous and next panels.</em>
        </div>
      </td>
    </tr>
    <tr>
      <td align="center"><strong>Kobo Support</strong></td>
      <td>
       <strong>Added Kobo physical buttons and page-turner device support (<a href="https://github.com/OGKevin/kobo.koplugin">kobo.koreader support as well</a>)</strong><br><br>
        Pressing a physical page-turn button (or a Bluetooth remote) past the last panel on a page <strong>should</strong> automatically turn the page and open the first panel of the next one. Going backward from the first panel does the same in reverse. Corner and zoom gestures on Kobo hardware <strong>should</strong> be recognized out of the box too, with no extra setup needed.<br><br>
        I say <em>should</em> because I tested this against the kobo.koreader repo and tried to emulate the Kobo environment <a href="https://github.com/KristanLaimon/PanelsPlus/blob/main/runkobo.sh">with a small script</a>. However, since I don't actually own a Kobo device, I'm flying a bit blind here! I hope it works flawlessly for you Kobo users. If it doesn't, please open an issue in this repo and I'll fix it ASAP.
      </td>
    </tr>
    <tr>
      <td align="center"><strong>Rotation Picker</strong></td>
      <td>
        <strong>Redesigned rotation menu</strong><br><br>
        The rotation button now opens a small visual picker with icons showing exactly how the page will be oriented for each option, instead of forcing you to cycle blindly through rotation states.<br><br>
        <div align="center">
          <video src="https://github.com/user-attachments/assets/cd59abe4-7c27-4210-8b89-a3472e856ba3" width="40%" controls muted autoplay loop playsinline></video>
          <br>
          <em>🎥 Opening the visual picker to select the exact screen orientation.</em>
        </div>
      </td>
    </tr>
    <tr>
      <td align="center"><strong>Improved Comics Support</strong></td>
      <td>
        <strong>Smarter panel detection</strong><br><br>
        Comic reading mode has been polished all around. It now applies automatically to CBR, CBZ, and PDF files. Tiny false "panels" with no real artwork (credit strips, footer rules, stray marks) used to show up as their own swipeable panels. This is now much less frequent, and detection is generally far more reliable on typical Western comic layouts than in previous versions of Panels+.<br><br>
        <div align="center">
          <video src="https://github.com/user-attachments/assets/35d2af95-e447-4b2d-9e89-71aa68c15894" width="40%" controls muted autoplay loop playsinline></video>
          <br>
          <em>🎥 Smooth, accurate panel-by-panel navigation on a Western comic layout.</em>
        </div>
      </td>
    </tr>
    <tr>
      <td align="center"><strong>Expanded Format Support</strong></td>
      <td>
        <strong>Increased support for .PDF, .CBR, and .CBZ files</strong><br><br>
        Panel+ now features enhanced, native support for standard comic formats (<code>.CBR</code>, <code>.CBZ</code>) and <code>.PDF</code> files. <br><br><em>⚠️ Please note: Formats like <code>.epub</code>, <code>.mobi</code>, and similar are not officially supported by this plugin. Please use standard formats to read your manga, as text-based formats are not designed for comics/manga</em>
      </td>
    </tr>
  </tbody>
</table>

</div>

The main focus of this release was your feedback! When I posted the [last version on Reddit](https://www.reddit.com/r/koreader/comments/1vbjx0z/release_panels_read_manga_through_panels_the_easy/), the biggest feature requests came from [Kobo users](https://www.reddit.com/r/koreader/comments/1vbjx0z/release_panels_read_manga_through_panels_the_easy/) and from folks who wanted [OCR-powered dictionary lookups](https://www.reddit.com/r/koreader/comments/1vbjx0z/comment/p0updf9/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button).

While I couldn't fit every single suggestion in—that would have taken forever, and I'm juggling other projects—I put a lot of effort into improving the overall experience, fixing obscure bugs, and adding several quality-of-life features.

## A Note on OCR Word Lookup

- **OCR is not installed by default.** Word lookup on comics/manga relies on KOReader's native OCR engine, which requires manual setup first. Please refer to the [KOReader OCR setup guide](PLACEHOLDER_OCR_SETUP_LINK) <!-- TODO: confirm/replace with the exact KOReader OCR install docs link -->.
- **It is genuinely experimental and can be flaky.** Reliably finding word boundaries in hand-lettered or stylized comic/manga text turned out to be a much harder problem than I anticipated (call it a skill issue on my part!). Expect the occasional incorrect word or missed tap.
- **Workaround:** While this stabilizes, I recommend binding a comfortable multi-swipe gesture to "Open dictionary lookup" as a fallback. It is much more reliable than the touch-and-hold OCR method for now.

And, an important QOL: When in zoom panning mode, now when trying to open koreader settings with a swipe down from top edge screen, it will (surprisingly) open the settings! instead of closing the panel and having to do the same gesture again.... 

And or course, even more improvements to memory/cpu usage in general.

## Fixes

- Prevented the detection of tiny false "panels" (such as credit strips, thin footer rules, or stray marks) that used to be rendered as empty, swipeable panels. This significantly improves the reading experience for comics and manga with non-standard layouts.
- Fixed an issue where word-lookup highlights appeared offset from the actual selected word.
- Fixed the OCR occasionally attempting to guess words from unreadable, noisy image crops instead of falling back to normal text selection.
- Fixed word/line highlight boxes occasionally rendering as large, solid black squares over the panel.
- Fixed the zoom-level label failing to update from "Original Size" to "Scaled" when zooming in.
- Fixed odd visual interactions between tap-based navigation and smooth panel transitions.
- Fixed a bug where swiping down on the left edge could unintentionally close the panel viewer instead of just zooming out.
- Implemented general stability and memory-usage improvements through internal code optimization and quality audits.

## Included Commits

- `477dae6` docs: Cleaning up readme
- `6f72250` feat: Added kobo.koplugin support for corner/zoom zoom gesture & page-turner events (bluetooth devices already included)
- `f3a8a97` submodule: Added testing dependency busted
- `03ae058` kobo-support: Added emulation script for kobo and generic devices
- `ecbb355` feat: Now PanelPlus apply to cbr, cbz and pdfs by default!
- `815b609` feat: Added initial code for text selection feature
- `356dc71` feat: Improved comics panel support (hard to do btw, experimental feature)
- `e08bb6d` feat: Improved and added word recognizing and dictionary look up (Works 50% of the times - EXPERIMENTAL)
- `00c163a` feat: Polished comic reading mode
- `46c52ec` feat: Improved dictionary words detection (still complicated to implement)
- `4419f52` chore: Deleting some .log files and ignoring internal docs
- `3fe62b7` feat: Added dark mode support
- `977322d` performance: Fixed some memory leaks due to last feat commits
- `afafa2d` feat: Added swipe and taps navigation additional config
- `88d83c3` fix: Fixed bug with "Original Size" not changint to "Scaled" when doing zoom
- `fd7bacc` fix: Fixed bug with tap navigation and smooth fps
- `7139db4` fix: Tune word-gap threshold and clamp vertical runaway in word finder
- `3ddaa4a` feat: Add OCR debug review mode for word-lookup accuracy
- `bb468d0` feat: Add OCR debug session report tool
- `e6dd100` fix: Mark touch & hold text selection as experimental in menu
- `2565231` Optimization and code audit
- `b4f4386` rotation: Improved rotation button option a lot

## Upgrading

Copy `panels_plus.koplugin` over your existing folder and restart KOReader. Your settings will be preserved! The new touch-and-hold text selection is disabled by default (marked as experimental in the menu), and all navigation and gesture options can be configured from the panel viewer's "More config..." menu.

## Author

- KristanLaimon
