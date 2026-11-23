<h1 align="center">Reading Pokédex for KOReader</h1>

<p align="center">Reach your daily reading goal in KOReader and a Pokémon appears in the book you’re reading.</p>

<p align="center">
  <strong>English</strong> · <a href="README.zh-CN.md">简体中文</a> ·
  <a href="docs/INSTALL.md">Installation guide</a> · <a href="#author">Author profiles</a> ·
  <a href="LICENSE">Original code (MIT)</a> · <a href="NOTICE.md">Asset rights</a>
</p>

<p align="center">
  <img src="sprites/sil/0054.png" width="84" alt="Silhouette of an uncaught Psyduck">
  <img src="sprites/0054.png" width="84" alt="A yellow Psyduck">
  <img src="sprites/shiny/0054.png" width="84" alt="A light blue Shiny Psyduck">
  <br>
  <sub>Pokédex #0054 · Psyduck, shown as an uncaught silhouette, a regular catch and a Shiny catch</sub>
</p>

## Meet your first Pokémon

1. **Install the plugin.** Quit KOReader and extract the GitHub source ZIP. Rename the folder containing `main.lua` to `pokemon.koplugin` and copy it into KOReader’s `plugins/` directory. Check that `plugins/pokemon.koplugin/main.lua` exists. KOReader’s built-in font works with the plugin.
2. **Open the Pokédex.** Restart KOReader, open a book and tap the top of the page. Select the Poké Ball tab **宝可梦图鉴 → 打开主面板** (Open dashboard). You can also find the plugin under **Tools → More tools → 宝可梦图鉴**.
3. **Choose a daily goal.** Open **每日目标** (Daily goal). The default is **30 minutes**, adjustable from **5 to 120 minutes**. Reading time adds up while a book is open and KOReader is awake. A catch card appears when you reach your goal.

For Kindle, Kobo and Android paths, updates, save backups and troubleshooting, see the [installation guide](docs/INSTALL.md).

## How your collection grows

| While you read | What happens in the plugin |
| --- | --- |
| Meet your daily goal | Earn one daily catch. Any catch can reveal a Shiny Pokémon. An egg hatches after three days of meeting your goal. |
| Meet a Pokémon again | Species that can evolve may do so on the third encounter. For Pokémon such as Eevee, you choose the evolution branch. |
| Read with a partner | Build affection with your partner, earn candy and complete daily quests. Finishing a book earns XP, candy, incense and an extra encounter. |
| Explore your Pokédex | Browse **1,025 species** across nine generations offline, filtered by generation or catch status. Menus and species names are in Simplified Chinese. |

## Author

**萧涵瑾** created and maintains the plugin.

[Xiaohongshu · @吱了个吱吱](https://xhslink.cn/o/7J3Y9htj3Sh) · [Douyin profile](https://v.douyin.com/vbHDGfxZBZc/) · [Bilibili · 吱了个吱吱-](https://b23.tv/vxks3K5)

## Reporting a problem

Include your device model, KOReader version, plugin build (shown on the dashboard) and steps to reproduce the problem. The save file `settings/pokemon.lua` and its backups may contain book titles and full paths. Redact those details before sharing an example. [Project issues](https://github.com/Gracezou/kindle-pokemon/issues)

## Copyright and license

This unofficial fan project is offered free of charge on a noncommercial basis. The original code for the reading timer, catch rewards and Pokédex interface, along with the original documentation, is © 2026 萧涵瑾 and licensed under MIT. [MIT License](LICENSE)

The Psyduck shown above and the Pokédex illustrations are drawn from PokéAPI’s sprite collection, which credits The Pokémon Company with the image copyright. Pokémon names, character designs and trademarks belong to their respective rights holders. Open-source and noncommercial status alone do not grant permission to use or redistribute these materials. [Third-party rights and credits](NOTICE.md)

On your device, open **宝可梦图鉴 → 玩法说明** (Pokédex → How to play) for the credits. When sharing copies or substantial portions of the original code, include the copyright and permission notices. The plugin folder carries both in its [offline copyright notice and full MIT License](COPYRIGHT.txt).
