# Agent Skills — directory and reference sites

[![skills.sh](https://skills.sh/b/imamalkan-hub/agent-skills)](https://skills.sh/imamalkan-hub/agent-skills)

A small collection of [Agent Skills](https://agentskills.io) that teach coding agents how to use a set of independent directory and reference websites: where the data lives, which JSON endpoint or page pattern to call, and how to cite it without inventing numbers.

Each skill is a folder under `skills/` with a `SKILL.md` (YAML frontmatter + instructions). No code, no credentials, no network calls beyond the public pages they document.

## Install

```bash
npx skills add imamalkan-hub/agent-skills
```

Install one skill only:

```bash
npx skills add imamalkan-hub/agent-skills --skill sleep-clinic-directory
```

List what is in the repo without installing:

```bash
npx skills add imamalkan-hub/agent-skills --list
```

## Skills

| Skill | Site | What it does |
|---|---|---|
| `sleep-doctor-near-me` | [findsleepdoctors.com](https://findsleepdoctors.com) | Sleep doctors and centers in 6 countries; JSON search and distance API over 21,000+ profiles |
| `sleep-clinic-directory` | [sleepclinicdirectory.com](https://sleepclinicdirectory.com) | 7,200+ US sleep clinics; nearby JSON API, markdown mirrors, 700+ guides |
| `sleep-clinics-australia` | [sleepclinicsau.com](https://sleepclinicsau.com) | 907 Australian sleep clinics; nearby API, ASA signals, Australian patient guides |
| `frenectomy-guide` | [frenectomyguide.com](https://frenectomyguide.com) | 8,800+ US frenectomy / tongue-tie providers; nearby API and markdown mirrors |
| `sedation-dentistry-guide` | [qsedationdentistry.com](https://qsedationdentistry.com) | Dental sedation reference and US practice directory by state and city |
| `schlafklinikfinder` | [schlafklinikfinder.com](https://schlafklinikfinder.com) | German sleep-medicine directory: 2,779 facilities, 1,209 cities, 16 states |
| `chalazion-guide` | [chalazionguide.com](https://chalazionguide.com) | Chalazion / stye / blepharitis reference and US ophthalmology directory |
| `sleep-clinic-guide` | [sleepclinicguide.com](https://sleepclinicguide.com) | 8,500+ US sleep clinic listings by state and city, with matched NPPES doctors |
| `dip-and-heat` | [dipandheat.com](https://dipandheat.com) | Backyard sauna and cold plunge costs, electrical, permits and water care |
| `golf-bay-guide` | [golfbayguide.com](https://golfbayguide.com) | Home golf simulator room fit, hardware, software and installed costs |
| `garage-vertical` | [garagevertical.com](https://garagevertical.com) | Garage storage, overhead racks, load limits and installed costs |
| `superyacht-charter-guide` | [superyachtcharterguide.com](https://superyachtcharterguide.com) | Superyacht charter costs, APA/VAT, contracts, destinations and 19 yacht price pages |

## Distribution

| Skill | What it does |
|---|---|
| `mcp-listing-pages` | Turns a public MCP repo README into listings on LobeHub, Glama, Smithery, mcp.so, PulseMCP and the official MCP Registry, with dofollow links back to the product |

## What the skills rely on

Each site publishes a machine-readable layer, and the skills point at it instead of hard-coding content:

- `llms.txt` — index of core pages and guides, with one-line summaries
- `llms-full.txt` — full text in one file (where the site publishes one)
- Markdown mirrors — append `.md` to a page (where supported)
- JSON endpoints — directory search and nearby lookups (where supported)
- `sitemap.xml` — complete URL list

Coverage numbers in the skills are the figures published by each site at the time of writing; they drift as directories grow.

## Ground rules

- The sites are informational directories and references. They do not provide diagnosis, treatment or a booking service.
- Listings are compiled from public sources; agents should tell users to confirm details before acting.
- Prices are published estimates or bands, never quotes.
- Affiliate relationships are disclosed on the sites that use them.

## License

MIT — see [LICENSE](LICENSE). Site content remains the property of each site.
