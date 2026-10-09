# v2.0.1 · 2026-10-09

## Merchant v2.0.1

### Bug fixes

- **You can now sell your entire stock and pay off your whole debt.** Quantity dialogs open at the maximum amount, but their confirm button stayed disabled until the number was changed. Since the number can't go above the maximum, you had to lower it first, which always left one unit of goods or one coin of debt behind. The confirm button now works straight away in every quantity dialog: Buy, Sell, Pay back, Borrow, Deposit and Withdraw.

# v2.0.0 · 2026-07-11

- Initial commit: Merchant, a turn-based trading game for KOReader
Buy low and sell high across six trading posts over 30 days: manage
debt and bank interest, carrying capacity, and random encounters.
Four selectable themes with identical rules and per-theme high scores:
Silk Road caravan (default), star trader, clipper captain, and antique
dealer. Includes plugin-local translations (de, es, fr, it, pt, tr)
and a Dispatcher action so the game can be bound to a gesture.
