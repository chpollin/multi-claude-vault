---
type: knowledge
vorschlag-id: V7
created: 2026-04-26
tags: [sugw, vorschlag, frontend, terminologie, inhalt]
stakeholder-issues: [S1, S2, S3, S4, S8, S9, S10]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/* (mehrere)
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/content/about.md
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/static/js/document.js
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/register.py
aufwand: "6-10h"
status: ready-for-implementation (mit User-Klärung)
author: Koordinator
implementation-commits: []
---

# V7 — Terminologie-Refactoring

## Problem

Stakeholder S1 (Querschnitt): "Terminologische Überarbeitung des Frontend." S2: kein "Wiener Urkundenbuch". S3: "Quellen", "Sammlungen", "Bestände" präzisieren. S4: "Überlieferungslücke" → "Auswertungslücke". S8 (Major): "Tod" → "als verstorben genannt". S9 (Major): Q-Kategorie aus öffentlichem Frontend ausblenden oder erklären. S10 (Major): "Factoids" als Bezeichnung passt nicht.

## Lösungsansatz

### Begriffs-Refactoring

Konsequent über alle Templates und JS-Module:

| Alt | Neu | Files |
|---|---|---|
| "Wiener Urkundenbuch" | "Quellen zur Geschichte der Stadt Wien" oder kontextspezifisch "Sammlung [Name]" | `about.md`, `index.html`, `startseite.html` |
| "Überlieferungslücke" | "Auswertungslücke" | `statistics.html`, `about.md`, `config.py` (`unprocessed_gaps`-Label) |
| "Tod" (als Kategorie / Spalten-Label) | "als verstorben genannt" | `register.py` (Label-Mapping), Templates wo angezeigt |
| "Factoids" / "Factoid" | "Erwähnungen im Regest" (Stakeholder-Review-pendent — Alternativen unten) | `document.js` (Funktion `buildFactoidTable` umbenennen oder Label-Mapping), `document.html` (Toggle-Button-Label), Glossar |
| "Quellenkorpus" / "Sammlung" | konsistente Verwendung gemäß Glossar (V6) | mehrere |

### "Factoid"-Ersatz — Stakeholder-Review-Block

Stakeholder lehnt "Factoid" ab, schlägt keinen Ersatz vor. Drei Kandidaten:

1. **"Erwähnungen im Regest"** — beschreibend, neutral, deckt Personen+Organisationen+Orte+Transaktionen ab.
   - Pro: präzise, nicht-fachsprachlich.
   - Contra: lang, mehrere Wörter.

2. **"Strukturierte Nennungen"** — kürzer, methodologisch klar.
   - Pro: kompakt.
   - Contra: "Nennungen" ist auch Fachsprache, unklar gegenüber S22 ("Nennungen" als Erwähnungs-Statistik).

3. **"Regest-Entitäten"** — fachsprachlich präzise (Person/Org/Place sind Entitäten in der DB).
   - Pro: korrekt im Datenmodell.
   - Contra: zu technisch für öffentliches Frontend.

**Empfehlung:** Variante 1 ("Erwähnungen im Regest") als Default; User holt Stakeholder-Bestätigung vor Phase 4. Falls anderer Vorschlag, Glossar-Eintrag in V6 entsprechend anpassen.

### Q-Kategorie-Hybrid

Stakeholder-Position S9: "Im Frontend sollte diese Kategorie so nicht sichtbar sein." Stakeholder nennt Erklärung als Alternative.

**Hybrid-Vorschlag (Stakeholder-Bestätigung pendent):**

1. `quality.html` aus Top-Nav-Dropdown "Projekt" entfernen — nicht mehr im öffentlichen Hauptpfad.
2. Page bleibt erreichbar via Direktlink für interne Reviewer (nicht 404, nicht entfernt).
3. Filter "Qualität" im Quellen-Index erhalten — er ist user-relevant ("Fehlerfrei / Hinweise / Warnungen") und nicht der eigentliche Q-Kategorie-Streitpunkt.
4. Optional: ein User-spezifischer Toggle "Interne Daten anzeigen" in einer Settings-Sektion (Phase-5+ Item).

### Inhalts-Refresh `about.md`, `statistics.html`, `edition-guidelines.html` (S15)

Stakeholder-Review-pendent — Inhalte sind **fachlich** zu überarbeiten (von Stakeholdern, nicht Subagent). V7 stellt nur das technische Substrat her: Markdown statt HTML inline, leicht editierbar, mit Glossar-Tooltip-Markierung.

## Akzeptanzkriterien

- [ ] "Wiener Urkundenbuch" kommt im Frontend nicht mehr vor (außer in historischen Quellenangaben, dort kontextualisiert).
- [ ] "Überlieferungslücke" überall durch "Auswertungslücke" ersetzt.
- [ ] "Tod"-Spalten-Label durch "als verstorben genannt" ersetzt (in Personen-Tabelle, in Detail-Seiten, in Beziehungs-Aggregat).
- [ ] "Factoid" / "Factoids" im UI durch User-bestätigten Ersatzbegriff ersetzt; Code-IDs (`factoid-toggle`, `buildFactoidTable`) refactored oder mit Mapping abstrahiert.
- [ ] `quality.html` aus Top-Nav entfernt, via Direktlink weiter erreichbar.
- [ ] Inhalts-Refresh `about.md` strukturell vorbereitet (Markdown plus Glossar-Marker), Inhalts-Update durch Stakeholder.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | grep "Wiener Urkundenbuch" im gerenderten HTML | gleicher grep | Alt: ≥1 Treffer. Neu: 0 |
| 2 | grep "Überlieferungslücke" | gleicher grep | Alt: ≥1. Neu: 0 |
| 3 | Personen-Tabelle Spalte "Tod" | gleiche Tabelle | Alt: "Tod"-Header. Neu: "als verstorben genannt"-Header |
| 4 | `documents/.../<id>.html` Factoid-Toggle | gleiche URL | Alt: Button-Label "Factoids". Neu: User-bestätigter Ersatzbegriff |
| 5 | Top-Nav "Projekt"-Dropdown | gleicher Hover | Alt: enthält "Qualität". Neu: "Qualität" entfernt; Direktlink `project/quality.html` weiter erreichbar |

## Risiken / Antipatterns

- **Antipattern:** Begriffsersatz nur in Templates, nicht im Glossar. Glossar (V6) muss synchron sein.
- **Antipattern:** "Factoid" hardcoded in Code (DOM-IDs `factoid-toggle`, `factoid-view`). Refactor Code-IDs **und** UI-Strings, sonst Drift.
- **Risiko Stakeholder-Dissens** beim "Factoid"-Ersatz: ohne Stakeholder-Bestätigung kann V7 Phase-4-Implementation rückwirkend anpassen müssen. **Aktion:** vor Phase 4 Stakeholder-Konsultation.

## Anschluss

- Stakeholder-Issues: S1, S2, S3, S4, S8, S9, S10.
- Verwandte V-IDs: V6 (Glossar speist Begriffe; muss synchron); V11 (Frontend-Polish — kleinere Inkonsistenzen).
- **User-Aktion vor Phase 4:** Stakeholder-Bestätigung für (a) "Factoid"-Ersatzbegriff, (b) Q-Kategorie-Hybrid.

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert. Status `ready-for-implementation (mit User-Klärung)` weil zwei Stakeholder-Entscheidungen pendent.
