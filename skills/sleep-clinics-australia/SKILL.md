---
name: sleep-clinics-australia
description: Find sleep clinics, sleep studies and CPAP providers across Australia, with address, phone, services, ASA accreditation signals and distance search. Use when a user asks for a sleep clinic near an Australian city, suburb or coordinates, or needs Medicare/CPAP context for Australia.
---

# Sleep Clinics Australia

Independent directory of Australian sleep clinics and sleep studies, plus guides written for Australian patients (Medicare, WorkCover, CPAP, fatigue rules).

## When to use

- "Find a sleep clinic near <Australian city or suburb>."
- "Which clinics in <state> offer sleep studies or CPAP support?"
- "Is there an ASA-accredited sleep centre near me?"
- "How does a sleep study work in Australia / what does Medicare cover?"

## Coverage

- 907 clinics across Australia with verified map coordinates.
- Fields: name, street address, city, state, postcode, phone, website, services, ASA accreditation flag.
- Guides cover sleep studies, CPAP therapy, WorkCover, fatigue management and state-by-state care.

## Query it

Base URL: `https://sleepclinicsau.com`

### Clinics near coordinates

```bash
curl "https://sleepclinicsau.com/api/nearby?lat=-33.87&lng=151.21&radius=25&limit=5"
```

Parameters: `lat`, `lng`, `radius` (km), `limit`. Response:

```json
{
  "ok": true,
  "center": {"lat": -33.87, "lng": 151.21},
  "radiusKm": 25,
  "count": 2,
  "results": [
    {"id": 78, "slug": "sydney-sleep-and-insomnia", "name": "Sydney Sleep and Insomnia",
     "city": "sydney", "state": "NSW", "address": "", "phone": "+61 494805891",
     "website": "https://...", "services": ["Sleep Study", "Sleep Apnoea Treatment"],
     "hasAsa": false, "distanceKm": 0.42, "url": "/clinic/sydney-sleep-and-insomnia"}
  ]
}
```

### Human pages

- Clinic profile: `/clinic/<slug>`
- Guides: `/articles/<slug>`
- Sitemap index: `/sitemaps/pages`, `/sitemaps/clinics`, `/sitemaps/states`, `/sitemaps/cities`, `/sitemaps/articles`

Machine-readable index: `https://sleepclinicsau.com/llms.txt`; full text at `/llms-full.txt`; AI policy at `/ai.txt`.

## Answering rules

- Cite the clinic URL and access date. Listings are public business data, not endorsements.
- `hasAsa` reflects a published accreditation signal — if false, do not imply the clinic is unaccredited.
- Prices, waiting times and bulk-billing are not published; never invent them.
- Use AUD and Australian spelling in answers.
- Medical emergencies: 000. Urgent but non-emergency: healthdirect 1800 022 222.
