---
name: frenectomy-guide
description: Find frenectomy, tongue-tie and lip-tie providers across the United States, and read plain-language guides on release surgery, laser technique and aftercare. Use when a user asks where to get a frenectomy or tongue-tie release near a US location, or what the procedure involves.
---

# Frenectomy Guide

Independent US directory of oral surgery practices that perform frenectomy and tongue-tie release, plus patient guides on techniques, aftercare and provider selection.

## When to use

- "Find a frenectomy or tongue-tie provider near <US city>."
- "Who does laser frenectomy / pediatric frenectomy in <state>?"
- "What happens during a tongue-tie release, and what is aftercare like?"
- "Compare providers by services and accreditation."

## Coverage

- 8,875 oral surgery clinics, all 50 states plus DC.
- 265 published guides on frenectomy, lip-tie, laser technique, infant aftercare and adult release.
- Profile fields: address, phone, website, services, accreditation signals, patient ratings.

## Query it

Base URL: `https://frenectomyguide.com`

### Clinics near coordinates

```bash
curl "https://frenectomyguide.com/api/nearby?lat=40.7&lng=-74&radius=25&limit=10"
```

Parameters: `lat`, `lng`, `radius` (km), `limit` (max 50). Response includes `results[]` with `name`, `city`, `state`, `phone`, `website`, `distanceKm` and `url`.

### Browse and markdown

- All providers: `/clinics` (60 per page)
- By state: `/states/<two-letter-code>`
- City finder: `/near-me`
- Guides: `/articles/<slug>`

Every page has a markdown twin — append `.md` (for example `/clinics.md`, `/clinic/<slug>.md`, `/states/ny.md`) or send `Accept: text/markdown`. Route catalog: `https://frenectomyguide.com/api/md/_catalog`.

Index: `https://frenectomyguide.com/llms.txt`. AI policy: `/ai.txt`.

## Answering rules

- Cite the clinic or guide URL and access date.
- Directory data is compiled from public sources; confirm services, ages treated and insurance by phone.
- Never state or imply a provider is "best"; list matching providers neutrally.
- Do not give a diagnosis. For infants with feeding problems, poor weight gain or bleeding, direct the user to a pediatric provider or urgent care.
- Patient ratings are not clinical quality measures.
