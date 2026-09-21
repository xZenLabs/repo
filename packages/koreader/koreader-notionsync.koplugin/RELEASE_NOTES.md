# v1.0.0

# NotionSync KOReader Plugin 1.0.0

## Installation

1. Download `notionsync.koplugin-1.0.0.tar.gz`
2. Extract to your KOReader plugins directory:
   ```bash
   tar -xzf notionsync.koplugin-1.0.0.tar.gz -C /path/to/device/.adds/koreader/plugins/
   ```
3. Eject your device and restart KOReader

Alternatively, download the artifact zip from this workflow run and extract the `notionsync.koplugin` folder directly to your plugins directory.

## What's Changed

## [1.0.0] - 2026-01-25

### Added

- Multi-database selection support - sync multiple Notion databases at once
- EPUB and Markdown output formats (EPUB is default)
- Rich text formatting preservation (bold, italic, strikethrough, inline code, links)
- Image embedding in EPUB files for full offline reading
- Image download caching to avoid redundant downloads within a sync session
- Automatic temp image cleanup after sync
- Sync history tracking to avoid re-syncing unchanged pages
- Format-specific sync tracking (switching formats triggers re-sync)
- Configurable save directory
- Network-aware sync (only runs when device is online)
- Progress indicators during sync with page-by-page updates
- Detailed sync statistics (new/old pages, image download counts)

### Features

- Sync Notion database pages to eReader for offline reading
- Support for multiple Notion databases simultaneously
- Automatic database discovery via Notion API
- Clean, simple UI integrated into KOReader's Tools menu
- Preserves Notion page structure and formatting
- Handles various Notion block types (headings, paragraphs, lists, quotes, code blocks, images)

<!--

---

**Full Changelog**: https://github.com/agluck91/koreader-notionsync/compare/0000000000000000000000000000000000000000...v1.0.0
