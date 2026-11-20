# DogEarBooks for KOReader

**DogEarBooks is a fork of [Book Nook Charms by KitanaCode](https://github.com/KitanaCode/booknookcharms.koplugin). The original project deserves credit and praise for its inventive approach to personalizing KOReader bookmarks. This fork adds the features and collections described below.**

DogEarBooks customizes the bookmark displayed on bookmarked pages while reading.

## Installation

1. Download the project and extract the archive.
2. Copy the plugin folder into KOReader's plugins directory, using this exact name:

   ```text
   koreader/plugins/dogearbooks.koplugin/
   ```

   Or Download from StoreFront

3. Restart KOReader, open a book, and find **dogearbooks** in the typesetting menu.
4. Bookmark a page to see your chosen image while reading.

Gesture availability can depend on your device and KOReader version.

## Gallery and folders

The library presents image previews across multiple pages. The **Folders** menu lets you browse individual collections and their subfolders.

For example, open **Folders**, choose **Movies**, and tap a preview to apply that bookmark. You can also choose an image from the gallery inside Charm Studio.

## Favorites

The **Favorites** menu shows collection folders and your saved favorites. Open a folder and hold a preview to add or remove it from your favorites. Tap a preview normally to apply it. You can also cycle through favorites using a gesture action.

For example, hold a bear in **bears**, then open **Saved Favorites** to find it alongside selections from other collections.

## Studio, position and size

**Charm Studio** lets you choose an image, adjust its size, and move it relative to the top and right edges. Use the buttons for incremental adjustments, or tap a position value to enter it with the keyboard. Position values range from 0 to 20.

For example, set the top position to 10, the right position to 2, and adjust the size. Press **Save** to keep your changes. When you select another image from the gallery or favorites, the current position and size are retained.

**Default** saves the current look as your default. **Cancel** restores the state from before you opened Studio. Reset options and looks saved for an individual book can apply their own settings.

The preview updates within the panel as you make changes. Touches stay within the panel, helping prevent accidental page turns during rapid adjustments.

## New collections

- **bears** contains six polar bear bookmarks, prepared as SVGs with transparent outer backgrounds.
- **Movies** contains stylized cinema-themed images, including Igor, Alien, Kill Bill, Charlie Chaplin, A Clockwork Orange, the Grinch, and Shining.
- **night/bears** and **night/Movies** contain corresponding versions for dark mode.

The artwork retains its internal black and white details. Transparent outer areas reveal the content underneath.

## Day and night

The **Day/Night Pair** menu lets you save an image for each mode and switch between them manually. You can also enable automatic switching when KOReader's night mode changes. Studio includes controls to save the current look as the day or night selection.

For example, choose a bear, adjust its position and size, then enable automatic pairing. For images in **bears** and **Movies**, the plugin can find the corresponding variant in the **night** folder when needed. Explicitly saved pairs take precedence and can have their own settings.

## Adding images and collections

Add files to an existing folder, such as `Movies/`, or create a dedicated folder inside `dogearbooks.koplugin/`. The plugin discovers folders and displays them in the **Folders** menu. Adding an image to a collection requires no code changes. Reopen the gallery after copying files.

You can also use `custom_icons/` or create collections in KOReader's data folder at `icons/booknookcharms/`. Supported formats include SVG, PNG, BMP, JPG, JPEG, and alpha files. The `ribbon_` prefix identifies ribbon-shaped bookmarks.

Example layout:

```text
dogearbooks.koplugin/
├── bears/
├── Movies/
├── custom_icons/
├── dogears/
├── ribbons/
├── night/
│   ├── bears/
│   └── Movies/
└── templates/
```

Automatic matching of the included variants is provided for **bears** and **Movies**. For a custom collection, you can select and save both images manually as a day/night pair.

## Language

The menu follows the language selected in KOReader. The fork includes translation catalogs for the languages present in the project. If a translation is unavailable, the plugin uses its fallback text.

## Drawing above reading information

The bookmark is drawn after the reader view's other elements, including Bookends text. Opaque parts of the image can cover that text, while transparent areas let it show through. Menus and dialogs remain accessible above the page. DogEarBooks handles the drawing order independently and does not require Bookends.

## Technical improvements

Gallery previews load progressively for the visible page. When the gallery closes, the plugin frees previews and cancels pending preview loading. Studio updates the reader view without reopening its panel for every adjustment.

Image loading uses checks and a fallback image when available. Saved paths can be repaired by searching for the filename. Automatic day/night switching follows night-mode events and requires no continuous polling loop. Existing settings and actions are preserved where possible after the plugin rename.

## Existing features

The fork retains ribbon and corner bookmarks, image categories, Studio presets, per-book looks, assignable gesture actions, and the **Troubleshooting** screen for checking settings. Availability of some features depends on the installed KOReader version.

## Credits and license

Original project created by **KitanaCode**. Fork modified by **Wolfazzo**. The original project credits the cat bookmarks to **u/AggravatingDebt4621**.

Distributed under the MIT license. See [LICENSE](LICENSE).

<img width="310" height="437" alt="ksnip_20261119-172153" src="https://github.com/user-attachments/assets/3258092e-cfbe-4884-abc5-386a5c86450b" />

<img width="310" height="438" alt="ksnip_20261119-172135" src="https://github.com/user-attachments/assets/f0faa219-71c4-4b15-97d0-eb41345124d6" />

<img width="308" height="437" alt="ksnip_20261119-172120" src="https://github.com/user-attachments/assets/177ea507-c98e-4204-b78b-bd87596f8cec" />

<img width="309" height="439" alt="ksnip_20261119-172101" src="https://github.com/user-attachments/assets/19817e8b-1902-4112-adcc-48bffc820354" />


