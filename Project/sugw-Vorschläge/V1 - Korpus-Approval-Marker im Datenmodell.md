---
type: knowledge
vorschlag-id: V1
github-issue: 1
created: 2026-04-26
updated: 2026-04-26
tags: [sugw, vorschlag, frontend, daten-modell]
stakeholder-issues: [S25, S26, S28, S29, S31, S37]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/config.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/pipeline/transformers/persons.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/pipeline/transformers/orglist.py
aufwand: "8-12h"
status: ready-for-implementation
author: Koordinator (Single-Curator, Synthese aus A+B+C)
implementation-commits: []
---

# V1 — Korpus-Approval-Marker im Datenmodell

## Problem

Stakeholder (S25, S26, S31): "Die angezeigten Daten dürfen nur aus den bereits geprüften Korpora stammen (= QGW, StB)." Aktuell ist der Approval-Mechanismus `RELEASED_CORPORA` in `edition/config.py` definiert und in `aggregator.py` über `_is_released_row` partiell angewandt — aber die Personen-/Organisations-/Orte-Aggregate tragen kein Korpus-Feld, und Korbinian-Daten außerhalb QGW/StB (S28) sind nicht systematisch markiert. Stakeholder-Forderung S37 ("Interface-Zahlen müssen mit DB übereinstimmen") wird damit verletzt.

## Lösungsansatz

### Datenseite

1. **`RELEASED_CORPORA` als Single Source bestätigen.** Aktuelle Liste in `edition/config.py`:
   ```python
   RELEASED_CORPORA = (
       "QGW/Vienna_1177-1414_ready",
       "QGW/Vienna_1415-1417",
       "Stadtbuecher/Band_1_1395-1400_ready",
   )
   ```
   **Achtung:** Stakeholder fordert nur QGW + StB als geprüft; QGW II/2 (1415-1417) ist laut Protokoll nicht freigegeben. **Klärung mit User vor Implementation:** ist `Vienna_1415-1417` versehentlich in der Liste oder bewusst? Bei Klärung "nicht freigegeben" → aus Liste entfernen.

2. **Approval-Marker pro Aggregat-Entität.** In `pipeline/transformers/persons.py` und Geschwister-Modulen ein Feld `released_corpora` (Liste der freigegebenen Korpora, in denen die Person/Org/Place vorkommt) zur CSV-Zeile hinzufügen. Aggregator nutzt das Feld zur Filterung in JSON-Aggregaten.

3. **`_is_released_row` Audit.** Alle Stellen in `aggregator.py` durchgehen und prüfen, ob `_is_released_row` konsequent vor jedem Aggregat angewandt wird. Aktueller Befund (Strang A): mindestens `persons_search.json` enthält Personen aus nicht-released Korpora ohne `c`/`corpus`-Feld zur Filterung.

### Build-Seite

- Beim Build wird ein Audit-Report `pipeline/output/approval_audit.md` erzeugt: pro Korpus die Anzahl der gerenderten Quellen, gerenderte Personen-/Org-/Place-Einträge, plus eine Liste der Personen/Orgs/Places, die ausschließlich in nicht-released Korpora vorkommen (= sollte aus Indizes verschwinden).

### Frontend-Seite

- Korpus-Chips in `documents.html` zeigen nur `RELEASED_CORPORA`. Nicht-released Pfade sind weder Chip noch direkt aufrufbar (404 oder Hinweis-Page).

## Akzeptanzkriterien

- [ ] `RELEASED_CORPORA` ist Single Source — eine Klärung mit User abschließend dokumentiert (welche Korpora gehören rein).
- [ ] `persons_search.json` enthält ein `c` (corpus) Feld pro Eintrag mit Liste der Korpora, in denen die Person erscheint (nur released).
- [ ] `aggregator.py` wendet `_is_released_row` auf **alle** JSON-Outputs an (`persons_search.json`, `organisations_search.json`, `places_search.json`, `search.json`, `timeline.json`, `epic_*.json`, `quality.json`).
- [ ] `pipeline/output/approval_audit.md` wird beim Build erzeugt und enthält Korpus-Stichproben.
- [ ] Personen, die nur in nicht-released Korpora erscheinen, sind nicht in `persons_search.json` (analog Org/Place).
- [ ] Korpus-Chips in `documents.html` zeigen nur released Korpora.
- [ ] Korbinian-Daten-Korpora (sofern in `sources/` vorhanden) sind explizit als nicht-released markiert.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `documents.html` Korpus-Chips | gleiche URL | Alt: 3 Chips inkl. QGW II/2. Neu: 2 Chips QGW II/1 + StB Bd. 1 (oder 3 nach User-Klärung) |
| 2 | `data/persons_search.json` direkt: Anzahl Einträge | gleiche URL | Alt: 16.084. Neu: deutlich weniger (geschätzt 10.000-12.000), weil Personen nur aus released Korpora |
| 3 | Suche im Personen-Index nach Person, die ausschließlich in QGW II/2 vorkommt | gleiche Suche | Alt: Treffer. Neu: kein Treffer (oder explizit gefiltert) |
| 4 | Build-Output `pipeline/output/approval_audit.md` | — | Datei existiert mit Korpus-Stichproben |

## Risiken / Antipatterns

- **Risiko Datenverlust:** Personen, die in QGW UND in nicht-released Korpus vorkommen, müssen erhalten bleiben (mit released-Korpus-Listing). Implementation darf nicht "Person hat irgendwo nicht-released Korpus" → Person raus filtern.
- **Antipattern:** TEI-Header pro Datei editieren. Ist 6.452-File-Operation mit Risiko für TEI-Validierung. Stattdessen Filter auf Aggregat-Ebene (pragmatisch).
- **Antipattern:** Approval-Status hardcoded in JS. Filter muss server-seitig (build-time) geschehen, sonst kann Frontend ungeprüfte Daten leaken.

## Anschluss

- Stakeholder-Issues: [[Findings/2026-04-26 - sugw Stakeholder-Feedback#S25]], S26, S28, S29, S31, S37.
- Daten-Architektur: [[Knowledge/sugw Daten-Architektur#Korpuskontrolle — was schon da ist (kritischer Befund)]].
- Verwandte V-IDs: [[Project/sugw-Vorschläge/V2 - Filterung der Indizes]].
- Verifikations-Doc (nach Implementation): `Project/sugw-Verifikation/V1-Verifikation.md`.

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert in Phase 2 nach Auswertung Strang A (Frontend-Inspektion bestätigt Filter-Lücke), Strang B (S25-S31 als Blocker), Strang C (Mechanismus existiert in `edition/config.py`). Status `ready-for-implementation` provisorisch — eine User-Klärung vor Phase-4-Start (welche Korpora wirklich released).
