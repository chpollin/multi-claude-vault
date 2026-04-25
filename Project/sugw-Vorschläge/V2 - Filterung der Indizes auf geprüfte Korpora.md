---
type: knowledge
vorschlag-id: V2
github-issue: 2
created: 2026-04-26
tags: [sugw, vorschlag, frontend, indizes]
stakeholder-issues: [S25, S26, S27, S29, S37]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/register.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/register_list.html
aufwand: "4-6h"
status: ready-for-implementation
author: Koordinator
implementation-commits: []
---

# V2 — Filterung der Indizes auf geprüfte Korpora

## Problem

S25/S26/S29/S37: Personen-/Organisationen-/Orte-Indizes und alle Statistik-Counter dürfen ausschließlich Daten aus released Korpora enthalten. S27: Personen ohne Dokument-Bezug (z.B. "Aaron der Jude") sollten nicht im Index erscheinen. Aktueller Stand laut Strang A: `persons_search.json` enthält 16.084 Einträge, kein Korpus-Feld, kein Filter — Personen aus QGW II/2 oder anderen ungeprüften Korpora sind enthalten.

## Lösungsansatz

Direkte Folge-Implementation aus V1. V1 baut den Korpus-Marker, V2 wendet ihn auf alle Indizes an.

### Aggregator

In `edition/aggregator.py` für jeden Index-JSON-Output:

1. **Eingangsfilter:** Vor Aggregation Eingangs-CSV-Zeilen mit `_is_released_row` filtern.
2. **Mention-Count berechnen pro Entität, nur aus released Korpora.** Personen-Aggregat enthält Feld `dc` (document_count) — Berechnung auf released-Subset einschränken.
3. **Index-Filter:** Personen mit `dc == 0` nach Korpus-Filterung aus dem Index ausschließen (S27).

### Frontend

- Personen-Index-Tabelle bleibt strukturell gleich, Daten kommen aus gefiltertem Aggregat.
- Filter "Quellenverknüpfungen" (aktuell "Alle / Mit Quellen") wird obsolet, weil Index nur noch Personen mit Quellenverknüpfungen zeigt — Filter entfernen.
- Optional: Hinweis-Banner "Diese Liste zeigt ausschließlich Einträge aus geprüften Korpora (QGW II/1 + Stadtbuch Bd. 1). Stand: <Datum>."

## Akzeptanzkriterien

- [ ] `persons_search.json` enthält ausschließlich Personen mit ≥1 Erwähnung in released Korpora.
- [ ] `organisations_search.json` und `places_search.json` analog gefiltert.
- [ ] `search.json` (globale Suche) filtert Quellen auf released Korpora.
- [ ] `timeline.json` zählt nur released-Korpora-Quellen pro Dekade.
- [ ] `quality.json` zählt nur released-Korpora-Findings.
- [ ] Personen-Index zeigt keinen Eintrag mit `dc == 0`.
- [ ] Stichprobe: vor Implementation bekanntes Stakeholder-Beispiel "Aaron der Jude" ist (a) im Frontend nicht mehr sichtbar wenn er keine released-Quelle hat oder (b) zeigt korrekte released-Quellen wenn er welche hat.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `register/persons.html` — Anzahl Einträge in Tabellen-Footer | gleiche URL | Alt: 16.084. Neu: signifikant weniger, ohne Personen aus nicht-released Korpora |
| 2 | Suche nach einer Person aus QGW II/2 | gleiche Suche | Alt: Treffer mit Quellen-Liste. Neu: kein Treffer im Index (oder Hinweis-Banner) |
| 3 | `data/timeline.json` Dekade 1410 (überschneidet QGW II/2) | gleiche Datei | Alt: höhere Counts. Neu: niedrigere Counts (nur QGW II/1 ≤ 1414) |
| 4 | `project/statistics.html` "16.084 individuelle Personen" | gleiche URL | Alt: 16.084. Neu: aktuelle Zahl nach Filterung |

## Risiken / Antipatterns

- **Riesige Diff in user-sichtbaren Zahlen.** Stakeholder muss vorab informiert sein, dass die Personen-Anzahl deutlich sinkt.
- **Antipattern:** Filter nur in Templates statt im Aggregator anwenden — Daten würden im JSON sichtbar sein, JS-Suche könnte ungeprüfte Daten leaken.

## Anschluss

- Stakeholder-Issues: S25, S26, S27, S29, S37.
- Voraussetzung: V1 (Approval-Marker) muss zuerst implementiert sein.
- Verwandte V-IDs: V8 (Statistiken), V3 (Suche).

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert. Sequenziell nach V1.
