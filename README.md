# Miami Spice 2026 — decoded

An unofficial value guide to [Miami Spice](https://www.miamiandbeaches.com/deals/spice-restaurant-months).
Every fixed-price menu, with each dish priced against the restaurant's own
everyday à la carte menu, so you can tell which deals actually save money and
what to order when you go.

**Live:** https://megabyte79.github.io/miami-spice/

Hobby project, not affiliated with the Greater Miami Convention & Visitors
Bureau or any restaurant.

## What is in here

| | |
|---|---|
| `index.html` | the whole guide, one self-contained file |
| `report.html` | error-report form |
| `build/` | the scripts and data the page is generated from |

## The numbers

- **682 menus** across **382 restaurants**, every tier
- **3,626 of 6,142 dishes** carry a real published price (59%)
- 2,824 of those came off the restaurant's own current menu

## How a verdict is decided

Each menu is scored against what the same food costs à la carte.

| | |
|---|---|
| ✓ Good however you order | every combination beats the price |
| ◆ Worth it only if you order right | the best picks beat the price by 15%+ |
| ▵ Barely worth it | close either way |
| ≈ At best, you break even | the best case lands on the price |
| ✕ Costs more than ordering normally | even the best picks lose |
| ⚑ Priced for a party | the tier buys more than one cover |
| ? Not enough published prices to judge | see below |

A dish carrying a supplement only counts for the difference: a $54 ribeye at
+$15 contributes $39 toward the base price, not $54.

## Why so many menus say "not enough prices"

About 40% of Miami Spice dishes have no published à la carte price, for reasons
that are mostly not fixable:

- **The dish only exists on the prix-fixe menu.** The largest single cause.
  There is no everyday price to compare against, by design.
- **The restaurant publishes no prices at all.** Verified across its own site,
  OpenTable, Resy and Yelp.
- **The menu has been rewritten** since the Spice listing was captured.
- **The item is genuinely unpriceable** — "chef's selection", market price, or a
  build-your-own pick spanning a wide range.

When a menu is not fully priced, the guide will not call it a good or a bad
deal. The dishes we could price are shown with their sources; the rest are shown
without a price. This matters: an early build scored a menu with *no* prices as
"worth $0, costs more than ordering normally", which is worse than saying
nothing.

The one verdict that survives incomplete data is **worth it if you order right**
— the priced dishes alone already beat the tier, so the missing ones can only
help.

## Prices move

Prices were verified in August 2026. Menus change during the program. Found
something wrong? The report form is linked from every card, and corrections show
up in the commit history.
