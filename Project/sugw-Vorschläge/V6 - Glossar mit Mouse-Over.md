---
type: knowledge
vorschlag-id: V6
created: 2026-04-26
tags: [sugw, vorschlag, frontend, glossar, inhalt]
stakeholder-issues: [S3, S5, S6, S7, S11, S15, S17]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/glossary.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/macros.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/static/js/tooltip.js (neu)
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/content/glossary.md (neu, falls Markdown-Pfad gewählt)
aufwand: "10-14h"
status: ready-for-implementation
author: Koordinator
implementation-commits: []
---

# V6 — Glossar mit Mouse-Over an Tabellen-Spalten

## Problem

Stakeholder S5 (Protokoll Z.4): "Glossar für die Website wäre sinnvoll." S6/S7 (Slide 2, Protokoll Z.10): "Solche Tabellen brauchen Mouse-Over Informationen zu den einzelnen Spalten." S11: Begriffe wie Quelle, Untersuchungskategorie erklären. S3: "Quellen", "Sammlungen", "Bestände" präzisieren. S17: Such-Semantik dokumentieren.

Strang A bestätigt: Glossar (`/project/glossary.html`) hat 9 Einträge — fehlen die zentralen Stakeholder-geforderten Begriffe. Tabellen-Header haben keine Tooltips. Statistik-KPIs haben `prov-popover`-Tooltips (saubere Pattern-Vorlage zum Wiederverwenden).

## Lösungsansatz

### Inhalt: Glossar-Begriffsliste

Mindest-Set für Phase-4-Implementation (im Stakeholder-Review zu finalisieren):

| Begriff | Definition (Entwurf, Stakeholder-Review pendent) |
|---|---|
| Quelle | Eine einzelne Urkunde, ein Brief oder ein anderer schriftlicher Zeuge mittelalterlicher Wiener Rechtsgeschäfte. Im Datenbestand entspricht eine Quelle einer TEI-XML-Datei mit eigener ID. |
| Sammlung | Bewusst zusammengestellter, thematisch oder örtlich gebundener Bestand mehrerer Quellen (z.B. das Wiener Stadtbuch). |
| Bestand | Gesamtheit der überlieferten Quellen einer Sammlung — unabhängig von der bisherigen Auswertung. |
| Korpus | Auswertungsfähig zusammengefasste Teilmenge des Bestands; trägt einen klar definierten Approval-Status. |
| QGW | "Quellen zur Geschichte der Stadt Wien" — Hauptkorpus der Edition. Aktuell freigegeben: QGW II/1 (1177–1414). |
| StB | Stadtbücher der Stadt Wien. Aktuell freigegeben: Stadtbuch Bd. 1 (1395–1400). |
| Untersuchungskategorie | Methodische Klassifikation, mit der ausgewählte Aspekte einer Quelle (z.B. Beteiligte, Transaktionsgegenstand) systematisch erfasst werden. |
| Regest | Strukturierte Zusammenfassung des Inhalts einer Urkunde mit Auszeichnung der relevanten Personen, Orte, Organisationen und Transaktionen. |
| Approval-Status | Zustand der fachlichen Prüfung eines Korpus. Nur freigegebene Korpora fließen in Indizes und Statistiken ein. |
| Auswertungslücke | Zeitabschnitt, für den noch kein freigegebenes Korpus vorliegt (nicht zu verwechseln mit Überlieferungslücke). |
| Q-Kategorie | Internes Qualitätsmerkmal von Datensätzen, primär für Reviewende. Im öffentlichen Frontend ohne Erklärung nicht aussagekräftig. |
| Erwähnung im Regest | (Ersatz für "Factoid", siehe V7) — strukturierter Hinweis auf eine Person, Organisation, einen Ort oder eine Transaktion innerhalb eines Regests. |
| Funktionsrolle | Rolle einer Person/Organisation in einer Transaktion (Aussteller, Empfänger, Zeuge, weitere). |
| Beziehung | Relation zwischen zwei Entitäten in der DB (Verwandtschaft, Geschäftsverbindung, Eigentumsbeziehung etc.) |

Erweiterung in Folge-Iterationen.

### Strukturen

1. **Single Source für Glossar.** Inhalt in `edition/content/glossary.md` (Markdown mit Frontmatter), bei Build in `glossary.html` und in JSON `docs/data/glossary.json` gerendert.
2. **Tooltip-Daten-Quelle.** `glossary.json`-Schema: `{ "term": { "id": "regest", "label": "Regest", "definition": "...", "anchor": "/project/glossary.html#regest" } }`.

### Tooltip-Komponente (Frontend-JS)

3. **`static/js/tooltip.js` (neu).** Web-Component oder leichtes JS-Modul, das `[data-glossary="regest"]`-Attribute findet und auf Hover/Focus eine Tooltip-Box mit Definition + Klick-Through-Link zum Glossar-Eintrag öffnet.

4. **Tabellen-Header-Anwendung.** In allen Tabellen (Quellen-Index, Personen-Index, Statistik-Tabellen): `<th data-glossary="..."><span>Spalten-Titel</span></th>`. Tooltip rendert via JS.

5. **Inline-Verwendung.** In Templates (`statistics.html`, `quality.html`, `documents.html`) erscheinen Schlüsselbegriffe mit unsichtbarem `data-glossary`-Wrap, Tooltip on hover. Per-Page-Konventionen: max. 1 Tooltip pro Begriff pro Page (gegen Tooltip-Spam).

### Glossar-Page-Layout

6. **`glossary.html`** als Tabelle plus Anker pro Begriff. Suche/Filter im Glossar selbst.

## Akzeptanzkriterien

- [ ] `glossary.md` enthält mindestens die 14 Begriffe aus der Liste oben (nach Stakeholder-Review finalisiert).
- [ ] `data/glossary.json` enthält strukturierte Definitionen.
- [ ] Tooltip-Komponente funktional an Tabellen-`th`-Elementen.
- [ ] Tooltip funktional auf Touch-Devices (Tap statt Hover).
- [ ] Glossar-Page zeigt alle Einträge alphabetisch mit Ankern.
- [ ] Stakeholder-Review-Note: vor Phase-4-Implementation Stakeholder-Bestätigung der Begriffsliste einholen.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `project/glossary.html` Anzahl Einträge | gleiche URL | Alt: 9 Einträge. Neu: ≥14 Einträge |
| 2 | Hover über Spalten-Header in `register/persons.html` | gleiche Aktion | Alt: nichts. Neu: Tooltip mit Spalten-Definition |
| 3 | Hover über "Regest" in `documents.html` Spalten-Header | — | Tooltip mit Regest-Definition |
| 4 | Klick auf Tooltip-Link führt zum Glossar-Eintrag | — | Navigation zum Anker |

## Risiken / Antipatterns

- **Risiko:** Tooltip-Overload — jedes Wort mit Tooltip wirkt belehrend. Mitigation: max. 1 Tooltip pro Begriff pro Page.
- **Antipattern:** Tooltips ohne Touch-Support. Mobile/Tablet-User können sonst nicht zugreifen.
- **Antipattern:** Glossar-Inhalt fest im Template (HTML inline). Single Source in Markdown/JSON.

## Anschluss

- Stakeholder-Issues: S3, S5, S6, S7, S11, S15, S17.
- Verwandte V-IDs: V7 (Terminologie — V6 liefert die Begriffe, V7 setzt sie ein).
- **User-Aktion vor Phase 4:** Stakeholder-Review der Begriffsliste.

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert mit Inhalt-Schwerpunkt (Claude-B-Domäne) und Tech-Anteil (Claude A für Tooltip-Komponente).
