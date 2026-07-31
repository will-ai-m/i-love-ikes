# Ike's Sandwich Catalog

A near-complete catalog of every named sandwich sold by **Ike's Love & Sandwiches**, compiled by pulling the online ordering menu of **all 116 US locations** and merging them into one deduplicated list — organized by the meat (or plant protein) that leads each build.

- **757** unique named sandwiches
- **116** store menus merged
- **20** protein groups
- Pulled **2026-07-23**

Ike's is famous for a menu that reportedly spans hundreds of combinations, but no single master list is published anywhere — the flagship website shows only ~30 items, and the rest live on individual store ordering pages (many of them regional or single-store exclusives). This repo reconstructs the full picture by scraping every location.

## Live site

**→ [will-ai-m.github.io/i-love-ikes](https://will-ai-m.github.io/i-love-ikes/)** — an interactive, searchable catalog of all 757 sandwiches, filterable by protein group, diet (meat / vegan / vegetarian), and any ingredient. Built from the data below.

## Files

| File | What it is |
|------|-----------|
| [`index.html`](index.html) | The live catalog site (self-contained; loads the JSON below) |
| [`SANDWICHES_BY_PROTEIN.md`](SANDWICHES_BY_PROTEIN.md) | Human-readable list, grouped by protein |
| [`data/ikes_sandwiches.json`](data/ikes_sandwiches.json) | Structured data (name, number, ingredients, protein group, store count) |
| [`data/ikes_sandwiches.csv`](data/ikes_sandwiches.csv) | Same data as CSV |

## Data fields

Each sandwich record has:

- **`number`** — Ike's own menu ID (e.g. `929`)
- **`name`** — sandwich name (e.g. `HALSEY`)
- **`protein_group`** — the category it's filed under (its headline protein)
- **`ingredients`** — listed fillings/sauces/cheeses
- **`locations_count`** — how many of the 116 stores carry it (a proxy for how core vs. regional it is)

## Protein groups

| Group | Count | Notes |
|-------|------:|-------|
| Halal chicken | 69 | All non-fried chicken at Ike's is halal |
| Fried chicken | 56 | |
| Chicken (other) | 2 | Tenders / odd chicken items |
| Turkey | 70 | Includes multi-meat deli combos led by turkey |
| Roast beef | 33 | Includes corned beef |
| Steak & beef | 60 | Steak, cheesesteak, chicken-fried steak, brisket |
| Pastrami | 32 | |
| Ham | 19 | |
| Salami | 7 | Beef salami as the lead |
| Meatball | 24 | All-beef meatballs |
| Bacon | 13 | Bacon as the headline protein |
| Seafood | 19 | Tuna, wild salmon burger, lobster salad |
| Sausage / hot link | 2 | |
| Vegan – chicken | 133 | Plant-based chicken (grilled & fried) |
| Vegan – turkey | 59 | |
| Vegan – steak | 27 | Plant-based steak / brisket |
| Vegan – meatball | 30 | |
| Vegan – bacon | 17 | Veggie bacon |
| Vegan – other | 4 | Vegan meatloaf, bulgogi, etc. |
| Vegetarian (no meat) | 81 | Eggplant, mushrooms, cheese, avocado, etc. |

## Method & caveats

- Source: Ike's online ordering menus (`oxb.pxsweb.com` / `orderexperience.net`), one menu API call per active location.
- Items are deduplicated by name, with trivial spelling variants of the same name (typos, plurals, punctuation, added first names or subtitles) merged into one entry. The same sandwich number sometimes carries genuinely different names at different stores (school/team tie-ins), and those are kept as distinct entries.
- **Protein grouping is derived** from each item's first-listed ingredient — multi-meat combos (e.g. Matt Cain: turkey + roast beef + salami) sit under their first-listed meat.
- Every Ike's sandwich comes hot on Dutch Crunch with dirty sauce, lettuce & tomato by default, and most meat builds can be made vegan on request.
- **Not exhaustive of everything Ike's has ever made** — in-store-only sandwiches beyond the app, and discontinued items, aren't captured. This is the full *online-orderable* catalog as of the pull date.

## License

Data is Ike's Love & Sandwiches' own menu content, reproduced here for reference. Not affiliated with or endorsed by Ike's.
