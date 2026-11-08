---
name: sleep-doctor-near-me
description: Find sleep medicine doctors, sleep centers and specialists by city, region or coordinates in the US, UK, Canada, Australia, Ireland and New Zealand. Use when a user asks for a sleep doctor, sleep specialist or sleep clinic near a place, or wants distance-sorted results. Covers 21,000+ profiles with a free JSON search API.
---

# Sleep Doctor Near Me

Directory of sleep medicine doctors and sleep centers across six English-speaking countries, with distance search and a free JSON API. Every profile is compiled from public sources: medical registries, health-service directories and hospital websites.

## When to use

- "Find a sleep doctor near me / near <city>."
- "Which sleep centers are in <state/region>?"
- "List sleep specialists within 25 km of <coordinates>."
- "What are the phone, address, languages or telehealth options for <doctor>?"

## Coverage

- 21,343 sleep specialists, 4,186 cities, 95 regions, 6 countries.
- Country codes: `us`, `gb`, `ca`, `au`, `ie`, `nz`.
- Fields: name, credentials, specialty, clinic, address, postcode, phone, website, coordinates, city, region, country.

## Query it

Base URL: `https://findsleepdoctors.com`

### Free-text or location search

```bash
curl "https://findsleepdoctors.com/api/search?q=sleep+apnea&location=Houston&limit=10"
curl "https://findsleepdoctors.com/api/search?country=gb&region=england&limit=20"
```

Parameters: `q`, `location`, `country`, `region`, `city`, `specialty`, `lat`+`lng`, `distance` (km, 1–500), `sort` (`distance|name|city`), `page`, `limit` (max 50).

Response shape:

```json
{
  "total": 10580,
  "page": 1,
  "pages": 3527,
  "doctors": [
    {"name": "...", "clinic": "...", "address_line": "...", "postcode": "...",
     "phone": "...", "website": "...", "lat": 0, "lng": 0,
     "city_name": "...", "region_name": "...", "country_code": "us"}
  ],
  "cities": [],
  "regions": [],
  "filters": {},
  "origin": {}
}
```

### Nearest doctors to coordinates

```bash
curl "https://findsleepdoctors.com/api/near-me?lat=29.76&lng=-95.36&radius=25"
```

Returns `origin`, `radius_km`, `cities[]` and `doctors[]` with distance in km. Radius defaults to 50 km, maximum 500.

### Turn a place name into coordinates

```bash
curl "https://findsleepdoctors.com/api/geocode?q=EH1+1Scotland&country=gb"
```

### Human pages

- Country: `/us`, `/gb`, `/ca`, `/au`, `/ie`, `/nz`
- Region: `/<country>/<region-slug>` (e.g. `/us/tx`)
- City: `/<country>/<region-slug>/<city-slug>` (e.g. `/us/tx/houston`)
- Doctor profile: `/<country>/<region>/<city>/<doctor-slug>`

Machine-readable index: `https://findsleepdoctors.com/llms.txt`, condensed full text at `/llms-full.txt`, usage policy at `/ai.txt`, all URLs in `/sitemap.xml`.

## Answering rules

- Cite the exact profile or city URL and the access date.
- Present results as directory listings, not endorsements or medical referrals.
- Phone numbers and websites come from public sources and can be stale — tell the user to confirm before travelling.
- Do not invent ratings, reviews, wait times or insurance acceptance; the directory does not publish them.
- For urgent symptoms, advise local emergency care instead of directory browsing.
