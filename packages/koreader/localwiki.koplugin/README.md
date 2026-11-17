# LocalWiki for KOReader

LocalWiki lets you read Wikipedia and other [Kiwix ZIM files](https://library.kiwix.org/)
without an internet connection. It works directly on Kindle, Kobo, Android,
PocketBook, and desktop KOReader.

## What you can do

- Search articles across all your local ZIM files.
- Open links and move back and forward between articles.
- Use offline Wikipedia from KOReader's text-selection lookup.
- Choose how many article images to show, from none to all.
- Use large archives, including split files on FAT32 devices.

## Install

1. Download the latest `localwiki.koplugin.zip` from
   [Releases](https://github.com/nar-io/localwiki.koplugin/releases).
2. Extract the `localwiki.koplugin` folder into KOReader's `plugins` folder.
3. Restart KOReader.

## Add an offline encyclopedia

1. Download a `.zim` file from the [Kiwix Library](https://library.kiwix.org/).
2. Create a `wikipedia` folder on your device storage.
3. Copy the ZIM file into that folder.
4. Open **Wikipedia (offline)** from KOReader's menu.

If a ZIM file is too large for FAT32 storage, split it with `split_zim.py`.
The plugin automatically recognizes the resulting `.zimaa`, `.zimab`, and
other parts as one archive.

## Settings

From the LocalWiki menu you can enable or disable individual archives and
choose the number of images shown in full articles. Your choices are saved
between KOReader restarts.

## License

This project is released under the
[CC BY-NC 4.0](LICENSE) license.
