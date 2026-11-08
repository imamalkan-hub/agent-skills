---
name: superyacht-charter-guide
description: Independent guides to chartering a superyacht or catamaran — weekly base rates, APA, VAT, tipping, insurance, contracts and destination budgets — plus published price bands for 19 named charter yachts. Use when a user asks what a yacht charter costs, how APA and VAT work, or what a specific yacht charters for.
---

# Superyacht Charter Guide

Independent, numbers-first guides to chartering a superyacht or catamaran: weekly base rates, APA, VAT, tipping, insurance, bareboat vs crewed, and destination budgets. Rates are published bands plus expenses; every figure names its source and date.

## When to use

- "How much does it cost to charter a superyacht / catamaran for a week?"
- "What is APA, and what does it cover?"
- "What does <yacht name> charter for, and what are its specs?"
- "Crewed vs bareboat, catamaran vs monohull — which fits my group?"
- "What should I budget for a charter in the Caribbean / Mediterranean?"

## Coverage

- 19 named charter yachts with published weekly bands, length, guest capacity and cruising areas.
- 31 published guides across cost, destinations, logistics, insurance, comparisons, cruise-club reviews and fleet-operator reviews.
- A charter cost calculator at `/calculator/` builds an all-in weekly price with APA, VAT and tips.

## Query it

Base URL: `https://superyachtcharterguide.com`

### Index first

```bash
curl "https://superyachtcharterguide.com/llms.txt"
```

Lists every hub, guide and yacht page with a one-line summary.

### Hubs

- Cost: `/cost/`
- Destinations: `/destinations/`
- Basics and contracts: `/logistics/`
- Insurance and risk: `/insurance/`
- Comparisons: `/compare/`
- Cruise-club products: `/cruise-club/`
- Fleet reviews: `/reviews/`
- Fleet index: `/yachts/`

### Yacht pages

Pattern: `/<yacht-name>-yacht-charter-price/` — for example `/alfa-nero-yacht-charter-price/`, `/maltese-falcon-yacht-charter-price/`, `/christina-o-yacht-charter-price/`.

### Guides

Pattern: `/<slug>/` — for example `/mega-yacht-charter-cost/`, `/luxury-sailing-yacht-charter-cost/`, `/below-deck-charter-cost/`.

No public JSON API and no markdown mirror — fetch the HTML pages listed in `llms.txt`.

## Answering rules

- Cite the exact page URL and access date.
- Present rates as published weekly bands plus APA, VAT and tip — never as a fixed quote or a booking price.
- Say what the figure includes and what it excludes; charter pricing changes with season, itinerary and yacht availability.
- Do not invent availability, broker terms or insurance cover.
- For a specific trip, recommend confirming with a central agent and reading the charter contract.
