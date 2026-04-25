---
type: knowledge
vorschlag-id: V4
github-issue: 4
created: 2026-04-26
tags: [sugw, vorschlag, frontend, personen-profil]
stakeholder-issues: [S21, S22, S27]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/register.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/register_placeholder.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/build.py
aufwand: "12-16h"
status: ready-for-implementation
author: Koordinator
implementation-commits: []
---

# V4 — Personen-Profile parallel zu Regesten

## Problem

Stakeholder-Blocker S21 (Slide 7, Protokoll Z.15): "Parallel zu dieser 'Regesten-View' muss es auch eine 'Person-View' geben." S22: Profil zeigt alle Regest-Erwähnungen, alle Beziehungen, Schreibvarianten. Strang A bestätigt: `register/`-Verzeichnis enthält nur `persons.html` als Tabelle, keine Detail-Pages pro Person. Verlinkung aus Urkunden geht auf Tabellenzeilen-Anker `register/persons.html#pe__...` — kein Person-zentrierter Kontext.

## Lösungsansatz

### Build-Pipeline

1. **Pro-Person-Aggregat in `aggregator.py`.** Neues JSON pro Person `docs/data/persons/<pe_id>.json` mit:
   - Stammdaten (id, n, fn, sn, sex, Lebensspanne aus Erwähnungs-Daten)
   - `mentions[]` — Liste aller Erwähnungen in released Korpora: `{doc_id, doc_date, doc_role, regest_excerpt}`
   - `roles_count` — Aggregat über Funktionsrollen (issuer, recipient, witness, ...)
   - `relations[]` — Beziehungen aus `*_relations_in_sources.csv` (kin, occ, owner, friend, rep, tenant, title-ref, topo, buis), mit Verlinkung auf verbundene Person/Org/Place
   - `schreibvarianten[]` — Original-Schreibungen aus `n` plus Mention-Varianten

2. **Page-Generator in `register.py` und `build.py`.** Pro Person eine HTML-Page `docs/register/persons/<pe_id>.html` rendern aus `templates/person_detail.html` (neu).

3. **Template `person_detail.html`.** Sektionen:
   - Header: Name, Lebensspanne, Geschlecht, Schreibvarianten
   - Erwähnungen: Tabelle aller Regest-Vorkommen mit Klick-Through
   - Beziehungen: gruppiert nach Beziehungstyp
   - Quellen-Korpora: aus welchem Korpus stammen die Erwähnungen (released-Marker)

4. **Routing-Anpassung.** Aus `register/persons.html` Tabellen-Zeile linkt auf `register/persons/<pe_id>.html` statt auf Anker.

### Frontend-Verlinkung

- Aus Urkunden-Detail (`document.html`-Template) linkt jede `<rs type="person">` auf `register/persons/<pe_id>.html`.
- Aus `persons_search.json` Suchergebnis-Klick führt zur Detail-Page.

### Pipeline-Optimierung

- Bei 16.084 Personen entstehen 16.084 HTML-Files. Mit released-Filter (V2 + V1) reduziert sich das auf ~10.000-12.000 — vertretbar (vergleichbar zu 5.715 Urkunden-Pages).
- Build-Inkrement: nur veränderte Personen neu rendern, wenn Pipeline das unterstützt.

## Akzeptanzkriterien

- [ ] Pro Person mit ≥1 Erwähnung in released Korpus existiert eine eigene HTML-Page `register/persons/<pe_id>.html`.
- [ ] Detail-Page zeigt: Stammdaten, alle Regest-Erwähnungen mit Verlinkung, Beziehungen, Schreibvarianten.
- [ ] Aus Urkunden-Detail klickbar zu Personen-Profil.
- [ ] Aus Personen-Index klickbar zu Personen-Profil.
- [ ] Test-Anker S20: "Simon Pötel"-Profil zeigt Regest 3819 in der Erwähnungs-Liste.
- [ ] Build-Output `docs/register/persons/`-Verzeichnis ist erzeugt.
- [ ] Bauzeit-Regression: Build-Zeit erhöht sich um nicht mehr als Faktor 2 (Stichprobe).

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `register/persons.html` Klick auf eine Person | gleiche Klick-Aktion | Alt: Anker-Sprung in selber Tabelle. Neu: Navigation zu eigener Detail-Page |
| 2 | URL `register/persons/pe__simon_poetel_*.html` | gleiche URL | Alt: 404. Neu: Detail-Page rendert |
| 3 | Detail-Page zeigt Erwähnungen | — | Liste aller Regeste mit Klick-Through |
| 4 | Detail-Page zeigt Beziehungen | — | Verwandtschaftsbeziehungen (für S20-Beispiel: Anna Pötlin als Frau erkennbar) |
| 5 | Aus Urkunden-Detail (z.B. `documents/QGW/Vienna_1177-1414_ready/3819.html`) Klick auf Person | gleicher Klick | Alt: Anker. Neu: Detail-Page |

## Risiken / Antipatterns

- **Risiko Build-Zeit-Explosion:** 16.000+ Detail-Pages. Mitigation: released-Filter sorgt für ~10-12k Pages, Inkrement-Build wenn Pipeline unterstützt.
- **Antipattern:** Detail-Pages JS-rendered statt static. GitHub Pages unterstützt nur statisches Hosting; Routing muss build-time geschehen.
- **Antipattern:** Detail-Pages ohne released-Filter. Die Detail-Page eines Person, die nur in nicht-released Korpus vorkommt, würde Daten leaken.

## Anschluss

- Stakeholder-Issues: S21, S22, S27.
- Voraussetzung: V1 + V2 (Filter-Mechanik), V5 (Beziehungs-Daten im Aggregat).
- Vermutete starke Synergie mit V5 — können in einem Implementations-Block parallel laufen.
- Test-Anker: Regest 3819, "Simon Pötel" / "Anna Pötlin".

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert. Größtes Volumen aller V-IDs.
