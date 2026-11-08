---
name: sleep-clinic-guide
description: Search 8,500+ US sleep clinics, sleep labs and sleep medicine practices by state and city, with address, phone, services and matched NPPES doctors. Use when a user asks for a sleep clinic near a US location, or for plain-language guides to sleep testing, apnea and CPAP.
---

# Sleep Clinic Guide

Independent directory of US sleep clinics, sleep labs and sleep medicine practices, plus plain-language guides to sleep testing.

## When to use

- "Find a sleep clinic near <US city / state>."
- "Which sleep labs are in <state>?"
- "What services does <clinic> list, and which doctors are matched to it?"
- "How do sleep studies, home tests and CPAP work?"

## Coverage

- 8,515 listings across 793 cities and 51 state codes.
- City pages exist where a city has at least 3 listings.
- Practice profiles: address, phone, services, matched NPPES doctors.
- Guides: sleep studies, sleep apnea, CPAP.

## Query it

Base URL: `https://sleepclinicguide.com`

### URL patterns

- All states: `/sleep-clinics/`
- State: `/sleep-clinics/<two-letter-code>/` (e.g. `/sleep-clinics/ca/`)
- City: `/sleep-clinics/<two-letter-code>/<city>/`
- Practice profile: `/clinic/<slug>/`
- Guides: `/blog/`
- Distance finder: `/near-me/` — runs in the browser with geolocation (15/25/45 miles); there is no JSON API.

Machine-readable index: `https://sleepclinicguide.com/llms.txt` (structure plus usage rules). Sitemaps: `/sitemap-clinics.xml`, `/sitemap-cities.xml`, `/sitemap-articles.xml`, `/sitemap-static.xml`.

### Workflow

1. Read `/llms.txt` for the URL grammar.
2. Resolve the state code, then open the state page; use the city links on it.
3. Fetch the clinic profile for address, phone, services and matched doctors.
4. For guides, pick from `/blog/`.

## Answering rules

- Cite the clinic or guide URL and access date.
- Listings are public business data; do not present them as endorsements.
- Do not invent prices, wait times or insurance acceptance.
- Matched NPPES doctors are a data link, not proof that the doctor currently works there.
- Medical emergencies: local emergency services, not the directory.
