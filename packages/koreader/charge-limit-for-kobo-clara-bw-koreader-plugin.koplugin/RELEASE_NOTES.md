# v2.0

## v2

- **Adaptive check interval.** Instead of a fixed 60-second check, the plugin now adjusts how often it checks based on how close the battery
  is to your threshold: every 5 minutes when far away, every 2 minutes when getting close, every 1 minute right before/after the limit. Same negligible battery/CPU cost but it's more professional this way. 

- **Immediate check on settings change.** Changing the charge limit threshold now re-checks and re-applies it right away, instead of
  waiting for the next scheduled check.

- **Fixed a scheduling edge case** where a check could get silently stuck and stop recurring if a pending timer didn't survive device suspend.

# Plugin

[chargelimit.koplugin.zip](https://github.com/user-attachments/files/31578375/chargelimit.koplugin.zip)
