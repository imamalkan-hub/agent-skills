---
name: chalazion-guide
description: Clinical reference on eyelid bumps — chalazion, stye, blepharitis and the differential — plus a US directory of ophthalmology practices by state and city. Use when a user asks what a chalazion is, how it is treated, whether a home remedy works, or where to find an eye doctor near them.
---

# Chalazion Guide

Independent clinical reference on chalazia, styes, blepharitis and other eyelid bumps, plus a directory of ophthalmology practices across the United States.

## When to use

- "What is a chalazion, and how is it different from a stye?"
- "Do warm compresses / antibiotics / surgery work for a chalazion?"
- "How much does chalazion removal cost?"
- "My child has an eyelid bump — what should we do?"
- "Find an ophthalmologist near <US state or city>."

## Coverage

- Condition pages: chalazion, stye, blepharitis, eyelid bump, removal, surgery cost, children.
- Treatment and home-remedy reviews with an evidence-first stance.
- US ophthalmology practice directory by state and city.
- Editorial policy and review standard are published on the site.

## Query it

Base URL: `https://chalazionguide.com`

### Pages

- Home: `/`
- All articles: `/blog/` (RSS at `/rss.xml`)
- Directory entry: `/near-me/`
- State: `/near-me/<state-slug>/` (e.g. `/near-me/california/`); city pages link from there.
- Article: `/<slug>/` (e.g. `/chalazion-treatment/`, `/chalazion-vs-stye/`, `/chalazion-surgery-cost/`)

Machine-readable index: `https://chalazionguide.com/llms.txt` — lists every core page and article with a one-line summary and reading path.

### Workflow

1. Read `/llms.txt` to select the article matching the question.
2. Fetch the page; answer with its specific guidance, evidence caveats and numbers.
3. For local results, open `/near-me/<state>/` and follow city links.

No public JSON API; use the HTML pages or the `llms.txt` index.

## Answering rules

- Cite the exact page URL and access date.
- Patient education only — no diagnosis, treatment plan or prescription.
- Red flags that need same-day care: vision loss or blurring, severe or worsening pain, fever, spreading redness, a bump that keeps bleeding or grows. Say this explicitly.
- Do not repeat home remedies as recommendations when the page says the evidence is absent.
- Directory listings are public business data, not endorsements; confirm insurance and availability.
