# v1.1.2 · 2026-11-18


- After a full refresh, the next update waits for it to end, so a tap right after a flash no longer leaves part of the screen white on a Kindle. The refresh mode is now chosen when the screen is painted, so the wait happens at the right moment and an update asked for during sleep no longer counts.
- If the screen cannot be drawn (it shows names and addresses that come from another device), a message takes its place, with the Close button, and the transfer stops, instead of a screen that cannot be used.

# v1.1.1 · 2026-11-10


- The module that keeps the e-reader awake, shared with other plugins, now also clears the marker its oldest versions kept in KOReader's cache folder after a crash. Book Drop never used that place, so nothing changes in use.

# v1.1.0 · 2026-11-10


- Texts on the screen and on the pages say "e-reader" instead of "Kindle", since the plugin runs on other e-readers too. The screenshots `.zip` is now called `screenshots.zip`.
- The screen with the QR code says the address can also be typed in any browser, on a computer too.
- Download All no longer freezes the request: the page says the `.zip` is being prepared and the download starts by itself when it is ready, while the e-reader shows the same message.
- The firewall rules accept only private networks, and a port left open by a crash is closed as soon as KOReader starts again.
- The power button now works with the screen open: the e-reader sleeps, and the transfer stops. The screen keeps the e-reader awake the way KOReader's own auto suspend does, instead of the setting that also blocked the power button.
- Book Drop and other plugins that keep the e-reader awake no longer let it sleep in the middle of each other's work.
- A screen that cannot open shows a message instead of closing KOReader, and stops everything it had started.
- The Back button closes the screen, on e-readers with buttons.
- Nothing is painted over the sleep screen while the e-reader sleeps.
- A connection that sends nothing is no longer closed for the time the e-reader screen was busy.

# v1.0.2 · 2026-11-08


- The Book Drop cover on the sleep screen while the plugin is open.

# v1.0.1 · 2026-11-05


- The approval question closes when sharing stops, and a tap outside it no longer counts as Deny.
- The device in use keeps its own connections, so other devices on the network cannot take them.
- The screenshots `.zip` is reused while the screenshots stay the same, checks free space first, and is never served incomplete.
- Covers and downloads no longer walk the whole books folder, and a received book no longer makes the screen read it again.
- Updates on the e-reader screen no longer flash the whole screen each time.
- Less memory per cover, and books without a cover are not opened again.
- Faster transfers, with several connections moving in the same moment.
- An upload refused while it is being sent now shows the reason instead of "connection lost".
- The length of a download comes from the file itself.
- Errors in requests go to KOReader's log.
