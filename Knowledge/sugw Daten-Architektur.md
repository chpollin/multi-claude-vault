---
type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [sugw, architektur, pipeline, frontend, daten]
status: active
author: Koordinator (Single-Curator)
---

# sugw Daten-Architektur

Synthese der Pipeline-Repo-Inspektion. Beschreibt den Datenfluss TEI → CSV → JSON → HTML und identifiziert die genauen Stellen, an denen die Stakeholder-Issues aus dem Protokoll ansetzen müssen. Strang C der Phase 1; Referenz für Claude A's Tech-Vorschläge in Phase 3.

## Zwei-Repo-Setup

| Repo | Pfad | Funktion |
|---|---|---|
| Pipeline | `c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions` | TEI-Quellen, Build-Code, Templates, Daten-Aggregation. Alle Implementations-Edits passieren hier. |
| Edition | `c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions_edition` | Build-Output für GitHub Pages. Wird vom Pipeline-`build` befüllt. NICHT direkt editieren. |

Implementation-Branch in Pipeline: `frontend-rework-2026-04` (Phase 4).

## Datenfluss in fünf Stufen

```
TEI-XML Quellen (sources/)
   ↓ python -m pipeline transform
CSV-Tabellen (pipeline/output/, 21 Dateien)
   ↓ python -m edition build
   ↓   - aggregator.py: CSVs → JSON-Aggregate
   ↓   - register.py: Personen/Orgs/Places-Detailseiten
   ↓   - renderer.py: TEI → HTML pro Urkunde
JSON-Daten (docs/data/) + HTML-Pages (docs/)
   ↓ git push (oder cp -r) ins Edition-Repo
   ↓
GitHub Pages
```

### Stufe 1 — TEI-Quellen

`sources/` enthält 6,452 aktive TEI-XML-Dateien, organisiert nach Korpus:

```
sources/QGW/
  Vienna_1177-1414_ready/done/    ← FREIGEGEBEN
  Vienna_1415-1417/               ← FREIGEGEBEN
  Vienna_1448-57_ready/           ← NICHT freigegeben
  Vienna_1458-66/                 ← NICHT freigegeben
  Vienna_1493-1500/               ← NICHT freigegeben
  Vienna_1524/                    ← NICHT freigegeben (abstracts only)
sources/Stadtbuecher/
  Band_1_1395-1400_ready/         ← FREIGEGEBEN
```

**Annotation Model (4 Levels):**

```
L1 Events       → <rs type="event" ref="#ev__*">
L2 Functions    → <rs type="fn" role="issuer|recipient|witness|other">
L3 Entities     → <rs type="person|org|place" ref="#pe__|#org__|#pl__*">
L4 Attributes   → <roleName type="occ|kin|title|prof|dead|rep|friend|topo|owner" corresp="#...">
```

ID-Konstruktion: Events `ev__`, Persons `pe__`, Orgs `org__`, Places `pl__`. Place-Referenzen primär via `@corresp` in `<roleName>`, nicht via `<rs type="place">`.

Register in `indices/`: `personList.xml` (16,084 Einträge laut persons_search.json), `orgList.xml`, `placeList.xml`.

### Stufe 2 — Pipeline-Transformation

`python -m pipeline transform` produziert 21 CSVs in `pipeline/output/`. 14 Transformer-Module + 2 Validatoren.

Wichtige CSVs für Frontend:
- `persons.csv`, `organisations.csv`, `places.csv` — Register-Stammdaten
- `persons_in_sources.csv`, `orgs_in_sources.csv`, `places_in_sources.csv` — Vorkommen pro Quelle
- `persons_in_events.csv`, `orgs_in_events.csv`, `places_in_events.csv` — Vorkommen pro Event
- `events_in_sources.csv` — Event-Liste
- `transactionsgoods_in_events.csv` — Transaktionsgegenstände
- `*_relations_in_sources.csv` — Beziehungen (kin, occ, owner, friend, rep, tenant, title-ref, topo, buis)
- `filenames.csv` — Pfade aller Source-Files
- `validation_report.json` / `.md` — Schema-Validierung

**Output-Format:** semicolon-delimited UTF-8 CRLF, 203,475 Datenzeilen total.

### Stufe 3 — Edition-Aggregation (`edition/aggregator.py`)

Liest Pipeline-CSVs und produziert client-seitige JSON-Aggregate in `docs/data/`. Hier wohnt die **Approval-Filterung** (siehe Korpuskontrolle weiter unten).

Output (`docs/data/`):
- `persons_search.json`, `organisations_search.json`, `places_search.json` — Such-Index für JS-Suche
- `search.json` — globale Suche
- `docs_lookup.json` — Urkunden-Lookup
- `epic_a.json` … `epic_d.json` — Visualisierungs-Daten (Datacube-inspiriert: meta + dimensions + measures)
- `quality.json` — Qualitäts-/Q-Kategorie-Daten
- `timeline.json` — Zeitachsen-Aggregat

Die JSON-Schemata: top-level `meta` (Provenienz, Dimensions, Measures), Entitätsreferenzen via kanonische IDs, JSON-LD-ready.

### Stufe 4 — Edition-Rendering (`edition/renderer.py`, `register.py`)

Jinja2-Templates in `edition/templates/`:
- `base.html` (Layout)
- `startseite.html`, `index.html`, `about.html`
- `document.html` (TEI → HTML pro Urkunde)
- `register_list.html`, `register_placeholder.html` (Register-Übersichten)
- `glossary.html` (Glossar — laut Protokoll: ausbaubedürftig)
- `analysis.html`, `statistics.html`, `quality.html`
- `exploration.html`, `exploration_networks.html`, `exploration_places.html`, `exploration_roles.html`, `exploration_transactions.html`
- `guidelines.html`
- `macros.html`

Inhalts-Markdown in `edition/content/`: `about.md`, `edition_guidelines.md`, `impressum.md`. (Glossar-Inhalt ist offenbar im Template inline; prüfen ob Markdown-Extraktion sinnvoll für V6.)

### Stufe 5 — Distribution

Build-Output in `docs/` (5,715 Dokument-Pages, 19,699 Register-Detail-Pages). Wird ins Edition-Repo synchronisiert (cp -r) und über GitHub Pages ausgespielt.

## Korpuskontrolle — was schon da ist (kritischer Befund)

**Approval-Mechanismus existiert bereits** in `edition/config.py`:

```python
RELEASED_CORPORA = (
    "QGW/Vienna_1177-1414_ready",
    "QGW/Vienna_1415-1417",
    "Stadtbuecher/Band_1_1395-1400_ready",
)

def is_released_corpus(path_key):
    return path_key in RELEASED_CORPORA
```

Plus `RELEASED_PERIOD`-Konstante (1177–1412 mit Extension auf 1414 für QGW II/1+II/2; Lücke 1418–1447 als `unprocessed_gaps`).

Plus Filter-Funktion `_is_released_row(row)` in `aggregator.py`, die laut Code-Header CSV-Zeilen auf "released" filtert.

**Kritische offene Fragen für Claude A in Phase 1+3:**

1. Wird `_is_released_row` auf **alle** Aggregate angewandt? Insbesondere auf `persons_search.json`? (Wenn das Frontend-JS gegen diese Datei sucht und dort 16,084 Personen drin sind, davon viele aus nicht-released Korpora, hat das Stakeholder-Problem hier seinen Ursprung.)
2. Werden in `register/persons.html` und Detail-Pages auch `is_released_corpus`-gefilterte Daten gezeigt?
3. Werden in `statistics.html` Quellen-Zählungen pro Dekade auf released-Korpora gefiltert?
4. Wo lebt die Liste **"alle anderen Korpora außerhalb QGW + StB"** — sind die in `RELEASED_CORPORA` korrekt abwesend, oder gibt es einen Fall wo eine andere Korpus-ID durchrutscht (z.B. Korbinian-Daten ohne korrekten Pfad-Schlüssel)?
5. Was ist mit Personen, die in **mehreren** Korpora vorkommen — wenn eine Person in QGW UND in einem nicht-released Korpus genannt wird, zählt nur die QGW-Nennung?

**Ableitung für V1, V2:**
- V1 (Korpuskontrolle / Approval-Marker) muss prüfen, ob `RELEASED_CORPORA`-Mechanismus durchgängig wirkt — wenn ja, ist V1 eher Doku-Aufgabe (Markierung ungeprüfter Daten als solche, sichtbar im Frontend für interne Reviewer); wenn nein, sind konkrete Lücken zu schließen.
- V2 (Filterung Indizes) ist die operative Konsequenz aus V1: alle Aggregations-Ausgänge in `aggregator.py` müssen `_is_released_row` durchziehen.

## Stakeholder-Issues → Pipeline-Stelle (Mapping-Vorschau)

Vorläufige Zuordnung; Claude A verifiziert in Phase 3:

| Stakeholder-Issue | Vermutete Stelle | V-ID |
|---|---|---|
| Suche findet 2/3–3/4 nicht | `docs/data/persons_search.json` Aggregator + Frontend-JS in `static/`; ggf. Felder `n`, `fn`, `sn` und Umlaut-Normalisierung | V3 |
| Personen-Profile fehlen parallel zu Regesten | `register.py` + `register_placeholder.html` — Detailseiten nicht erzeugt? Oder erzeugt aber nicht verlinkt? | V4 |
| Bidirektionale Verlinkung Person ↔ Urkunde | Daten-Aggregat um Urkunden-Liste pro Person erweitern, Template-Slot in Person-Detail | V5 |
| Nur QGW + StB anzeigen | `aggregator.py` `_is_released_row`-Anwendung prüfen | V1, V2 |
| Q-Kategorie zu intern | Frontend-Anzeige in `register_list.html` / Detail; ggf. flag im Template | V7 (Inhalt) + tech-Anteil V2 |
| Statistiken: % statt absolut | `aggregator.py` Decade-Aggregat; `epic_*.json`-Schema | V8 |
| Verb-Browser Aggregation | `transactionsgoods_in_events.csv` → Aggregator; Verb-Normalisierung in `normalisation_lists/` | V9 |
| "Tod" → "als verstorben genannt" | `roleName type="dead"`-Behandlung in `register.py`; Template-Label | V7 |
| "Factoids" Begriff | Template-Label in `document.html` | V7 |
| Glossar fehlende Begriffe | `glossary.html` + ggf. `edition/content/` ergänzen | V6 |
| Orte-Exploration weglassen | `exploration_places.html` aus Navigation entfernen oder Template auf "in Bearbeitung" | V10 |
| Transaktionen irreführend | `exploration_transactions.html` mit Kontext / Approval-Hinweis | V10 |

## Build-Befehle (für Phase 4)

```bash
cd "C:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions"

# 1. Pipeline (TEI → CSV)
python -m pipeline transform --validate

# 2. Edition (CSV → JSON + HTML)
python -m edition build

# 3. Lokal serven (Phase-4-Server auf 8766)
cd docs
python -m http.server 8766 --bind 127.0.0.1
```

(Annahme: `docs/` ist der Build-Output. Pipeline-README bestätigt: "Output: Static HTML in `docs/` (5,715 document pages, 19,699 register detail pages, ...)".)

## Test-Infrastruktur

- `python -m pipeline test` — Regressions-Tests
- `python -m pytest edition/tests/` — Edition-Tests
- `python -m pipeline dashboard` — strukturierte Test-Übersicht

Bei Implementation in Phase 4 unbedingt nach jedem V-Eingriff Tests laufen lassen.

## Knowledge-Base im Pipeline-Repo

`knowledge/`-Ordner im Pipeline-Repo enthält weiterführende Dokumentation:
- `architecture.md` — Pipeline-Architektur
- `data.md` — Daten-Inventar und Qualität
- `design.md` — Designentscheidungen
- `journal.md` — Projektverlauf
- `plan.md` — Implementations-Plan
- `system_prompt_tei_annotation.md` — TEI-Annotation-Konventionen
- `ui.md` — UI-Konzept
- `visualization.md` — Visualisierungs-Konzept

Für tieferen Kontext beim Implementieren: diese Files konsultieren. Insbesondere `ui.md` und `visualization.md` für V3-V10-Vorschläge relevant.

## Offene Fragen (für Synthese-Phase 2)

- **Ist die Pipeline-Approval-Filterung tatsächlich überall angewandt** oder nur in einigen Aggregaten? Claude A muss das in Phase 1 testen (z.B. ob persons_search.json Personen aus `Vienna_1493-1500` enthält).
- **Wo lebt der Glossar-Inhalt aktuell** — im `glossary.html`-Template inline oder als Markdown in `content/`? Beeinflusst V6-Implementations-Pfad.
- **Korbinian-Daten** (laut Protokoll: "für die Dissertation von Korbinian außerhalb QGW + StB erhoben"): in welchen Korpus-Pfaden liegen die? Sind sie überhaupt in `sources/` oder werden sie via `data_export/` reingebracht?
- **Mehrfach-Vorkommen** (Person in mehreren Korpora): wie ist das im aktuellen Daten-Modell abgebildet?

## Anschluss

- [[MISSION]] — Project-Fork-MISSION mit den 5 Erfolgskriterien.
- [[Project/sugw-frontend-rework Roadmap|Roadmap]] — Phasen.
- [[Project/sugw-Subagent-Prompts]] — Aufgaben für Claude A und B.
- [[Findings/2026-04-26 - sugw Frontend-Inspektion]] (geplant von Claude A) — wird IST-Befund liefern, gegen den dieses Doc das SOLL erklärt.
- [[Findings/2026-04-26 - sugw Stakeholder-Feedback]] (geplant von Claude B) — Stakeholder-Anforderungen.
- Pipeline-Repo: `c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/`.
- Edition-Repo: `c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions_edition/`.
