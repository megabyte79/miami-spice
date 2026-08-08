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
| `build/` | the generator, the scoring engine, the validators and the data |
| `LICENSE` | MIT for the code, CC BY-NC-SA for the research |

The generator is city-agnostic. Everything specific to Miami lives in
`build/city.json`: the programme name, dates, tiers, meals, source
attribution and one accent colour. The same code builds the
[Dine Out Lauderdale guide](https://megabyte79.github.io/dineout-lauderdale/).

```
python3 build/scoring.py  .        # recompute every derived field
python3 build/validate.py .        # data gates
python3 build/render.py   .        # write index.html
node     build/qa.mjs     .        # browser checks, both themes
```

## The numbers

- **680 menus** across **381 restaurants**, every tier
- **7,035 of 7,153 dishes** carry a price (98%)
- **4,812 are real published prices** — 3,597 an exact match on the
  restaurant's own current menu, 1,215 a rename or close variant
- **2,223 are benchmarked estimates**, each anchored to named priced dishes
  and shown with its working
- 118 dishes could not be priced honestly at all

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

## Where the estimates come from

About 30% of Miami Spice dishes have no published à la carte price, for reasons
that are mostly not fixable:

- **The dish only exists on the prix-fixe menu.** The largest single cause.
  There is no everyday price to compare against, by design.
- **The restaurant publishes no prices at all.** Verified across its own site,
  OpenTable, Resy and Yelp.
- **The menu has been rewritten** since the Spice listing was captured.
- **The item is genuinely unpriceable** — "chef's selection", market price, or a
  build-your-own pick spanning a wide range.

Rather than leave those blank, each one carries a **benchmarked estimate**. The
anchor is, in order of preference: a priced dish in the same course at the same
restaurant, a priced dish elsewhere on that restaurant's menu, or the same dish
at a named comparable restaurant in the same neighbourhood at the same price
level. Every estimate shows its working, so you can see what it was priced
against and disagree.

Estimates are marked. The dot on each card says whether its prices are verified,
partly estimated, or mostly estimated, and the source line under each dish says
which it is.

Two things the guide will not do with an estimate:

- **Take a price off a prix-fixe menu.** That is the tier price, not the dish
  price, and using one makes a good deal look like a wash. This is checked
  automatically on every price in the build.
- **State a verdict more firmly than the data allows.** When a call rests on
  estimates and sits close enough to the line that one of them could flip it,
  the card says "Likely" and its verdict wears a dashed border. 152 of the 680
  menus are marked that way.

11 menus still say **not enough published prices to judge**. Those are the ones
where a whole course has no price at all and no honest comparator existed.

## Prices move

Prices were verified in August 2026. Menus change during the program. Found
something wrong? The report form is linked from every card, and corrections show
up in the commit history.
