# Miami Spice 2026 — decoded

An unofficial value guide to [Miami Spice](https://www.miamiandbeaches.com/deals/spice-restaurant-months).
Every fixed-price menu, with each dish priced against the restaurant's own
everyday à la carte menu, so you can tell which deals actually save money and
what to order when you go.

**Live:** https://megabyte79.github.io/miami-spice/

Hobby project, not affiliated with Greater Miami Convention & Visitors Bureau or any restaurant.

## What is in here

| | |
|---|---|
| `index.html` | the whole guide, one self-contained file |
| `report.html` | error-report form |
| `build/` | the generator, the scoring engine, the validators and the data |
| `LICENSE` | MIT for the code, CC BY-NC-SA for the research |

The generator is city-agnostic. Everything specific to Miami lives in
`build/city.json`: the programme name, dates, tiers, meals, source attribution
and one accent colour. The same code builds the [Dine Out Lauderdale guide](https://megabyte79.github.io/dineout-lauderdale/).

```
python3 build/schema.py   .    # normalise to the canonical field set
python3 build/scoring.py  .    # every derived field
python3 build/validate.py .    # data gates
python3 build/render.py   .    # write index.html
node     build/qa.mjs     .    # browser checks, both themes
```

## The numbers

- **680 menus** across **381 restaurants**, every tier
- **7,032 of 7,153 dishes** carry a price (98%)
- **4,809 are real published prices**, 3,595 an exact match on the
  restaurant's own current menu and 1,214 a rename or close variant
- **2,223 are benchmarked estimates**, each anchored to named priced dishes
  and shown with its working
- 121 could not be priced honestly at all

## How a verdict is decided

Each menu is scored against what the same food costs à la carte.

| | | |
|---|---|---|
| ✓ Good however you order | every combination beats the price | 428 |
| ◆ Worth it only if you order right | the best picks beat the price by 15%+ | 210 |
| ▵ Barely worth it | close either way | 20 |
| ≈ At best, you break even | the best case lands on the price | 5 |
| ✕ Costs more than ordering normally | even the best picks lose | 6 |
| ⚑ Priced for a party | the tier buys more than one cover | 0 |
| ? Not enough published prices to judge | a whole course has no price | 11 |

A dish carrying a supplement only counts for the difference: a $54 ribeye at
+$15 contributes $39 toward the base price, not $54.

**"Likely"** in front of a verdict, with a dashed border, means the call rests
partly on benchmarked estimates and sits close enough to the line that one of
them could change it. 152 of the 680 menus are marked that way. The
verdict is still our reading of the numbers; the wording says how firmly.

## Where the estimates come from

Some dishes have no published à la carte price, for reasons that are mostly not
fixable: the dish exists only on the fixed-price menu, or the restaurant
publishes no prices anywhere, or the item is genuinely unpriceable.

Rather than leave those blank, each carries a **benchmarked estimate**. The
anchor is, in order of preference: a priced dish in the same course at the same
restaurant, a priced dish elsewhere on that restaurant's menu, or the same dish
at a named comparable restaurant in the same area at the same price level. Every
estimate shows its working, so you can see what it was priced against and
disagree.

Two things the guide will not do:

- **Take a price off a fixed-price menu.** That is the tier price, not the dish
  price, and using one makes a good deal look like a wash. Checked
  automatically on every price in the build.
- **Quote a saving whose sign contradicts its own verdict.** Also checked, on
  every card, every build.

## Prices move

Prices were verified in August 2026. Menus change during the program. Found
something wrong? The report form is linked from every card, and corrections show
up in the [commit history](https://github.com/megabyte79/miami-spice/commits/main).
