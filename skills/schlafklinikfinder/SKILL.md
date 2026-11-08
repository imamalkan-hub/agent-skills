---
name: schlafklinikfinder
description: Deutsches Verzeichnis schlafmedizinischer Einrichtungen — Schlaflabore, schlafmedizinische Praxen, HNO-Praxen und Kliniken in 1,209 Städten und allen 16 Bundesländern, plus Ratgeber. Use when a German-speaking user asks for a sleep clinic, sleep lab or sleep specialist in Germany, or about sleep studies and CPAP in Germany.
---

# Schlafklinik Finder

Unabhängiges Verzeichnis schlafmedizinischer Einrichtungen in Deutschland, ergänzt um einen medizinischen Ratgeber. Öffentliche Verzeichnisdaten und Anbieterangaben; keine medizinische Beratung.

## When to use

- "Schlafklinik / Schlaflabor in <Stadt> gesucht."
- "Welche schlafmedizinischen Einrichtungen gibt es in <Bundesland>?"
- "Wer behandelt Schlafapnoe / Insomnie in meiner Nähe?"
- "Wie läuft eine Schlafstudie in Deutschland ab, und was zahlt die Kasse?"

## Coverage

- 2,779 Einträge in 1,209 Städten, 16 Bundesländern.
- Einrichtungen: Schlaflabore, schlafmedizinische Praxen, HNO-Praxen, Kliniken.
- Profile: Adresse, Telefon, Schwerpunkte, Karte.
- Ratgeber: Artikel mit Quellen und FAQ.

## Query it

Basis-URL: `https://schlafklinikfinder.com`

### URL-Muster

- Einstieg: `/schlafmedizin/`
- Alle Bundesländer: `/bundeslaender/`
- Bundesland: `/bundesland/<slug>/` — Städte des Bundeslandes
- Alle Städte: `/staedte/`
- Stadt: `/schlafmedizin/<stadt>/` — Einrichtungen der Stadt mit FAQ
- Einrichtung: `/schlafmedizin/<stadt>/<einrichtung>/`
- Schwerpunkte: `/schwerpunkte/`, `/schwerpunkt/<slug>/`
- Ratgeber: `/ratgeber/`, `/ratgeber/<slug>/`
- Suche: `/suche/` (clientseitig, kein JSON-Endpunkt)
- Umkreissuche: `/kliniken-in-der-naehe/` (clientseitig, Standortfreigabe nötig)

### Workflow

1. `https://schlafklinikfinder.com/llms.txt` lesen — enthält die Struktur und alle Einstiegspunkte.
2. Bei Ortsfragen die Stadtseite `/schlafmedizin/<stadt>/` öffnen und Einrichtungen daraus beantworten.
3. Bei Bundesland-Fragen `/bundesland/<slug>/` nutzen, nicht die Sitemap durchsuchen.
4. Für eine Umkreissuche ohne Browser-Kontext: Stadtseite wählen oder `sitemap.xml` nach Städten filtern.

Es gibt keinen öffentlichen JSON-Endpunkt; die Daten stehen in den HTML-Seiten.

## Answering rules

- Quelle mit vollständiger URL und Abrufdatum nennen.
- Bewertungen sind öffentliche Durchschnittswerte, kein Urteil der Seite — nicht als Qualitätsurteil wiedergeben.
- Keine Preise, Wartezeiten oder Kassenzusage erfinden; Angaben vor einem Besuch beim Anbieter prüfen.
- Keine medizinische Diagnose; bei akuten Beschwerden auf ärztlichen Notdienst (116 117) oder 112 verweisen.
- Antwortsprache: Deutsch, wenn der Nutzer Deutsch schreibt.
