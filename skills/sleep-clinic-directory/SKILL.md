---
name: sleep-clinic-directory
description: Search 7,200+ US sleep clinics and sleep labs by state, city or coordinates, with address, phone, services, accreditation signals and patient ratings. Use when a user needs a sleep study, sleep center, CPAP provider or clinic near a US location. Includes a JSON nearby API and markdown mirrors of every page.
---

# Sleep Clinic Directory

Independent directory of sleep medicine clinics in the United States, plus plain-language guides to sleep studies, sleep apnea and CPAP therapy.

## When to use

- "Find a sleep clinic near <US city or ZIP>."
- "Which sleep labs in <state> offer <service>?"
- "What is the phone number / address for <clinic>?"
- "Compare accredited sleep centers before I book a sleep study."

## Coverage

- 7,246 clinics, all 50 states plus DC.
- Profiles carry address, phone, website, services, accreditation signals and patient ratings.
- 700+ published guides on sleep studies, apnea, CPAP and costs.

## Query it

Base URL: `https://sleepclinicdirectory.com`

### Clinics near coordinates

```bash
curl "https://sleepclinicdirectory.com/api/nearby?lat=40.7&lng=-74&radius=25&limit=10"
```

Parameters: `lat`, `lng` (required), `radius` in km (1–100, default 25), `limit` (max 50).

```json
{
  "ok": true,
  "center": {"lat": 40.7, "lng": -74},
  "radiusKm": 25,
  "count": 3,
  "results": [
    {"id": 21072, "slug": "...", "name": "Mount Sinai Center for Sleep Medicine",
     "city": "Brooklyn", "state": "NY", "phone": "(929) 210-6000",
     "website": "", "distanceKm": 0.87, "url": "/clinic/mount-sinai-center-for-sleep-medicine-brooklyn-ny"}
  ]
}
```

### Browse without coordinates

- All clinics: `/clinics` (paginated, 60 per page)
- By state: `/states/<two-letter-code>` (e.g. `/states/ny`)
- City index: `/near-me`
- Guides: `/articles`, `/articles/<slug>`

### Markdown mirrors

Every page has a markdown twin — append `.md`:

```bash
curl "https://sleepclinicdirectory.com/clinics.md"
curl "https://sleepclinicdirectory.com/clinic/<slug>.md"
curl "https://sleepclinicdirectory.com/states/ca.md"
```

Or send `Accept: text/markdown`. The machine-readable route catalog is at `https://sleepclinicdirectory.com/api/md/_catalog` (JSON, includes addressable counts and route patterns) — treat it as the authoritative route list and build links from `https://sleepclinicdirectory.com` yourself.

Full text: `https://sleepclinicdirectory.com/llms-full.txt` (~500 KB). Index: `/llms.txt` (if its links show a non-public hostname, ignore the host and keep the path). AI usage policy: `/ai.txt`.

## Answering rules

- Cite the clinic profile URL and access date; say the listing is directory data, not a referral.
- Services and accreditation are self-reported or compiled from public sources — tell the user to confirm insurance and availability by phone.
- Ratings are patient-submitted; never present them as clinical quality scores.
- Do not add wait times, prices or insurance coverage that the page does not state.
- Medical emergencies go to local emergency services, not the directory.
