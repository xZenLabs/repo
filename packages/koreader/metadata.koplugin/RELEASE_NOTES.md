# v0.1.0 · 2026-11-09

## Changes

- Add Open Library and AniList metadata sources, adapted from PR #4 with contributor credit.
- Correct Douban author biographies and field parsing; improve Google Books and Bangumi detail retrieval and metadata persistence.
- Improve cover handling, request cancellation, and recovery from failed searches.
- Move settings to `Search` → `Metadata` and use native centered loading messages.

## Installation

Download `metadata.koplugin.zip`, extract it into KOReader’s `plugins/` directory, and restart KOReader. Keep the `metadata.koplugin` directory intact. Open a book’s file actions and choose `Search metadata`.

For Google Books, long-press `Google Books` under `Search` → `Metadata` → `Sources` to set a personal [API key](https://developers.google.com/books/docs/v1/using). Requests without a key may hit shared quota limits.

## Validation

Provider search, details, metadata writes, cover decoding, and UI flows were checked in the native KOReader runtime. This release has not been verified on a physical device.
