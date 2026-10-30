<picture>
  <source media="(prefers-color-scheme: dark)" srcset="media/hero-light.png">
  <source media="(prefers-color-scheme: light)" srcset="media/hero-dark.png">
  <img alt="Silverfish: the egg, nymph, young, adult and elder, and the elder asking: I evolved for this?" src="media/hero-dark.png">
</picture>

# Silverfish

**Lives in your e-reader. Eats what you read. Judges your taste.**

*Em português: [LEIAME.md](LEIAME.md).*

Silverfish hatches from an egg after your first pages. It feeds only on pages you actually read, grows through four stages, and slowly becomes what you read. A reader of science fiction raises a paranoid little futurist. A reader of satire raises a critic who rolls her eyes at prefaces.

![The same silverfish growing up: nymph, young, adult, elder](media/growing-up.png)

It runs on your e-reader with **no AI and no internet**. Everything it says is put together on the device from what you read, and your reading never leaves the device.

![Three silverfish. Fed on horror: “If I met Lucy, I'd run.” Fed on romance: “If I met Darcy, I'd ask for an autograph.” Fed on mystery: “If I met Holmes, I'd bite.”](media/if-i-met.png)

## What it does

- **It eats what you read.** Every page you read for a few seconds becomes food. Skimming doesn't count. If you stop reading, it gets hungry, then grumpy, and eventually hides in the book's spine until you come back.
- **It grows up.** Egg, nymph, young, adult, elder. After about 2,000 pages it lays an egg and dies, and goes into the family **lineage** with its favourite quote and last words. The new silverfish is born with its mother's obsession and 30% of her personality.
- **It becomes what you read.** It picks up the world of your books: 16 literary influences, from sci-fi, satire and horror to romance, mystery, poetry and philosophy. Its personality also follows your habits: night reading makes a night owl, sad books make it bitter, adventures make it bold.
- **It gets obsessed.** One theme takes over (death, love, science, politics…), shown at the top of its diary, and it changes as your reading changes.
- **It notices the book.** It knows the characters, the words, the places and what happens in each chapter. It comments on the chapter, quotes what characters said, and reviews every book you finish.
- **It keeps a diary** of your reading days, and a **notebook** with your highlights.
- **It dreams.** Turn on its sleep screen, and when your e-reader sleeps you'll see it asleep, dreaming about what you read. Each stage has its own sleeping drawing.
- **Achievements and a bookshelf** with every book you finished together.
- **Portuguese and English.** It follows KOReader's language, or you can choose.

![“After Dracula, I need a light on and a long silence.” “After Pride and Prejudice, I need a handkerchief and a long silence.” “After The Hound of the Baskervilles, I need a cigarette and a long silence.”](media/after-the-book.png)

![“Old and frightened. A fine result of your literary taste.” “I've gone soft. It was your romances. Tell no one.”](media/your-taste.png)

## Install

**Before you start:** you need KOReader on your e-reader. On a Kindle, that means a jailbroken Kindle with KOReader installed, usually opened from KUAL. KOReader's own guide explains how: [KOReader wiki](https://github.com/koreader/koreader/wiki).

1. Download `silverfish-v1.0.0.zip` from [Releases](../../releases) and unzip it. Inside there is a folder called `silverfish.koplugin`.
2. Connect your e-reader to your computer and copy `silverfish.koplugin` into KOReader's `plugins` folder:
   - **Kindle:** `koreader/plugins/`
   - **Kobo:** `.adds/koreader/plugins/`
   - **Android:** `koreader/plugins/` in internal storage
   - **Other devices:** the `plugins` folder inside your KOReader folder
3. Restart KOReader.

**If you tested the beta** (a folder called `traca.koplugin`), delete that folder before copying the new one, and never keep both. Your silverfish survives the switch, because its progress lives in another file.

## Using it

- **Just read.** The egg hatches after a few pages.
- **To see it:** open the Tools menu and tap **Silverfish**. The welcome screen also lets you open it when KOReader starts, or with a long press in the top right corner.
- **Its screen** has a menu with its diary, your notebook, achievements and the lineage.
- **Tap it** to pet it. **Long-press it** for settings: sleep screen on/off, and language.
- **Optional:** with the [Simple UI](https://github.com/doctorhetfield-cmd/simpleui.koplugin) plugin (by doctorhetfield-cmd) installed, it shows up as a card on your home screen.

<img src="media/simple-ui.png" alt="A Kindle showing KOReader's home screen with the Simple UI plugin: the book being read, and below it the elder silverfish saying: chiming. Ate it. Nobody uses that word anymore.">

## Sleep screen

<img src="media/sleep-screen-photo.jpg" alt="A Kindle on a bookshelf, asleep, with the silverfish asleep on the screen and dreaming: dreaming in a big old house… a whole library… and I'm not even hungry…">

When your e-reader goes to sleep, Silverfish goes to sleep too, and dreams about what you read: the characters, the words, the places and the books themselves. Each stage has its own sleeping pose, and the egg just rests.

![The silverfish asleep at each stage: nymph, young, adult, elder](media/sleep-stages.png)

**To turn it on:**

1. Open Silverfish (Tools menu → **Silverfish**).
2. Long-press the silverfish.
3. Tap **Sleep screen: off**. It switches to **on**.

To turn it off, do the same. While it's on, Silverfish uses KOReader's sleep screen; when you turn it off, the sleep screen you had before comes back.

## Your data

Everything stays on your device, in `koreader/settings/traca.lua`: the titles and authors of the books you read, pages and reading times, its diary, a few lines from characters that it saved, and the path of the last book you opened. Silverfish never connects to the internet and never sends anything anywhere.

## Updating and backups

Your whole silverfish (its stage, personality, diary and lineage) lives in one file: `koreader/settings/traca.lua` (on Kobo, `.adds/koreader/settings/traca.lua`). The plugin folder holds no part of it.

**To update:**

1. Close KOReader and connect your e-reader to your computer.
2. Copy `koreader/settings/traca.lua` somewhere safe on your computer, just in case.
3. Delete the old `silverfish.koplugin` folder from `koreader/plugins/` and copy in the new one.
4. Start KOReader. Your silverfish picks up where it left off.

Never delete `traca.lua` when updating: that file *is* your silverfish. Every new version is made to open saves from older ones.

**Moving to another device:** install the plugin there, then copy your `traca.lua` into the same folder on the new device, with KOReader closed.

**If something goes wrong:** with KOReader closed, put your copy of `traca.lua` back in `koreader/settings/`.

## Uninstalling

1. If its sleep screen is on, turn it off first: long-press the silverfish and choose **Sleep screen: off**.
2. Delete `koreader/plugins/silverfish.koplugin`.
3. To erase the silverfish and its diary too, delete `koreader/settings/traca.lua` and the `koreader/traca` folder.

## Compatibility

Tested on KOReader 2026.07.1 on a Kindle Paperwhite 11. It should work on any device that runs KOReader (Kobo, PocketBook, Android), but those haven't been tested yet. If you run it on one of them, please say how it went in [Issues](../../issues).

**On Kindle:** start KOReader the way you usually do (from KUAL or its shortcut); nothing else changes. Silverfish only sees what you read in KOReader, not in Amazon's own reader, and its sleep screen shows when your Kindle goes to sleep with KOReader open.

Silverfish never blocks your reading. If something goes wrong, it says it tripped and stays quiet until you restart KOReader. In that case, please open an issue and attach `koreader/crash.log`.

## Known limits

- In books without a table of contents, it counts a chapter every 25 pages.
- It reads the book through its words; it doesn't understand the story like a person. Sometimes a comment about the chapter misses the point.
