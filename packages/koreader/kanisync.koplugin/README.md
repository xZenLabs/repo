# Kanisync

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![GPL-3.0 License][license-shield]][license-url]

A KOReader plugin to sync your reading progress with [AniList](https://anilist.co)

[Report Bug](https://github.com/Saterz/kanisync.koplugin/issues/new?labels=bug&template=bug-report---.md) &middot; [Request Feature](https://github.com/Saterz/kanisync.koplugin/issues/new?labels=enhancement&template=feature-request---.md)

## About The Project

> [!WARNING]
> This plugin is a WIP and is currently in a highly unstable state. Use at your own risk. I will assume no liability for any damage or data loss caused by the use of this plugin.

## Getting Started

### Prerequisites

- An [AniList](https://anilist.co) account. You can signup at [https://anilist.co/signup](https://anilist.co/signup)

### Installation

#### Recommended: ZenPM

ZenPM is a package manager for KOReader plugins. It is the recommended way to install Kanisync because adding the custom repository ensures you receive new versions as soon as they are released.

1. Install [ZenPM](https://github.com/xZenLabs/zen-pm) if you have not already.
2. Open ZenPM's **Sources** screen and add `https://zenpm-repo.saterz.dev`.
3. Refresh the sources, then find and install **Kanisync**.

#### Other options

- Install Kanisync from a third-party KOReader plugin app store.
- Download the latest release from the [GitHub Releases page](https://github.com/Saterz/kanisync.koplugin/releases) and install it manually.

### Configuration

1. Get your access token from [this link](https://anilist.co/api/v2/oauth/authorize?client_id=40345&response_type=token).
2. On a computer, create `settings/Kanisync/anilist_token.key` in the KOReader installation directory if it does not already exist.
3. Add your AniList access token from the redirect URL to `anilist_token.key` as plain text and safely eject your device.
4. Start using the plugin!

## Usage

TBD

## Contributing

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the GPL-3.0 License. See `LICENSE` for more information.

## Contact

Saterz - [contact@saterz.dev](mailto:contact@saterz.dev)

## Acknowledgments

This plugin would have not been possible without these awesome projects:

- [KOReader](https://koreader.rocks)
- [AniList](https://anilist.co)

[contributors-shield]: https://img.shields.io/github/contributors/Saterz/kanisync.koplugin.svg?style=for-the-badge
[contributors-url]: https://github.com/Saterz/kanisync.koplugin/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Saterz/kanisync.koplugin.svg?style=for-the-badge
[forks-url]: https://github.com/Saterz/kanisync.koplugin/network/members
[stars-shield]: https://img.shields.io/github/stars/Saterz/kanisync.koplugin.svg?style=for-the-badge
[stars-url]: https://github.com/Saterz/kanisync.koplugin/stargazers
[issues-shield]: https://img.shields.io/github/issues/Saterz/kanisync.koplugin.svg?style=for-the-badge
[issues-url]: https://github.com/Saterz/kanisync.koplugin/issues
[license-shield]: https://img.shields.io/github/license/Saterz/kanisync.koplugin.svg?style=for-the-badge
[license-url]: https://github.com/Saterz/kanisync.koplugin/blob/main/LICENSE
