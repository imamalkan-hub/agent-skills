---
name: dip-and-heat
description: Numbers-first guides to backyard saunas and cold plunge tubs — installation, electrical requirements, permits, water care, running costs and product comparisons. Use when a user asks what a sauna or cold plunge costs to buy or run, whether a backyard setup is feasible, or how to fix water problems in a cold plunge.
---

# Dip & Heat

Independent, numbers-first guides to backyard saunas and cold plunge tubs: real costs, electrical and permit requirements, water care, and honest product comparisons.

## When to use

- "What does it cost to install / run a backyard sauna or cold plunge?"
- "Do I need a dedicated circuit, permit or foundation?"
- "Best cold plunge under $1,000 / best sauna under $5,000?"
- "Why is my cold plunge water cloudy / green / smelly, and how do I fix it?"
- "Harvia vs Finlandia, Ice Barrel vs Plunge, Sun Home vs Redwood."

## Coverage

- Hubs: `/sauna/`, `/cold-plunge/`
- Guides cover buying, sizing, electrical load, permits, foundations, water chemistry (pH, ozone, UV, hydrogen peroxide), winterizing, insurance, resale and cost by state.
- A first-year and monthly running-cost calculator lives at `/calculator/`.
- The site publishes a methodology page and an affiliate disclosure; treat product mentions as disclosed affiliate links, not independent endorsements.

## Query it

Base URL: `https://dipandheat.com`

### Index first

```bash
curl "https://dipandheat.com/llms.txt"
```

It lists every hub and guide with a one-line summary — use it to choose the right page instead of guessing slugs.

### Full text in one file

```bash
curl "https://dipandheat.com/llms-full.txt"   # ~500 KB, every guide concatenated
```

### Markdown mirrors

Append `.md` to a page path:

```bash
curl "https://dipandheat.com/sauna.md"
curl "https://dipandheat.com/best-sauna-under-5000.md"
curl "https://dipandheat.com/cold-plunge-ph.md"
```

Sending `Accept: text/markdown` to a normal page returns the markdown version too. Each mirror starts with a `Canonical:` line — cite that URL.

## Answering rules

- Cite the exact guide URL and access date.
- Quote prices as estimates with the guide's stated basis (US average electricity rates, typical heater sizes) — never as a quote.
- Electrical and permit questions: give the guide's numbers, then tell the user to confirm with a licensed electrician and local building department.
- Affiliate relationships are disclosed on the site; do not describe product picks as unbiased lab tests.
- Cold-plunge safety: no unsupervised use, no alcohol, no long exposures; cardiac and pregnancy cautions belong in the answer when relevant.
