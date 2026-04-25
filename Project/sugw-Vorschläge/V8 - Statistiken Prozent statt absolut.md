---
type: knowledge
vorschlag-id: V8
created: 2026-04-26
tags: [sugw, vorschlag, frontend, statistik]
stakeholder-issues: [S12, S13, S26, S37]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/statistics.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/static/js/statistics.js
aufwand: "8-10h"
status: ready-for-implementation (mit Datenbasis-Klärung)
author: Koordinator
implementation-commits: []
---

# V8 — Statistiken: % statt absolut, Relation zum Gesamtbestand

## Problem

S12 (Slide 2): "Hier werden die bereits ausgewerteten Bestände gezeigt, besser wäre es, das in Relation zum Gesamtbestand anzuzeigen. Bsp: Grauer Balken im Hintergrund für alle Regesten, blauer Balken für bereits ausgewertete." S13 (Protokoll Z.9): "Es ist weniger wichtig auszuweisen, wie viele Quellen es pro Dekade gibt, sondern wichtiger, wie viel Prozent der Bestände in der jeweiligen Dekade ausgewertet wurden." S26: Statistiken nur für released Korpora. S37: Interface-Zahlen müssen mit DB übereinstimmen.

Strang A bestätigt: `data/timeline.json` ist Dekaden-basiert mit `{total, QGW, Stadtbuecher}` als absolute Counts. KPIs auf `statistics.html` sind absolut ("2.635 Quellen", "16.084 Personen").

## Lösungsansatz

### Datenbasis-Klärung (vor Implementation)

**Kritische offene Frage:** Was ist "Gesamtbestand pro Dekade"? Drei Interpretationen:

- (a) Anzahl ALLER überlieferten Wiener Quellen pro Dekade (auch außerhalb der Edition) — externe Recherche-Daten nötig.
- (b) Anzahl der Quellen aus dem Bestand der Edition (released + nicht-released zusammen) — aus dem Repo ableitbar.
- (c) Gesamt-Sollwert pro Dekade aus Stakeholder-Schätzung — Stakeholder-Eingabe nötig.

**Empfehlung:** Variante (b) als pragmatischer Default für Phase 4; Stakeholder-Klärung dokumentieren falls (a) gewünscht. Variante (b) ist transparent: zeigt das Verhältnis "released vs. noch zu prüfender Bestand" — ehrlich gegenüber Stakeholder.

### Aggregator (Pipeline)

1. **Erweiterung `timeline.json`-Schema.** Pro Dekade:
   ```json
   {
     "decade": 1300,
     "released": { "QGW": 42, "Stadtbuecher": 0, "total": 42 },
     "all_in_repo": { "total": 58, "released": 42, "unreleased": 16 },
     "ratio_released_pct": 72.4,
     "label_period": "1300–1309"
   }
   ```

2. **`released` und `all_in_repo` aus Pipeline-CSVs.** `_is_released_row` getrennt von Total-Aggregat. Bei Variante (a) externe Daten als zusätzliches CSV einbinden.

3. **Audit-Konsistenz.** Jeder Statistik-Wert im JSON wird gegen `pipeline/output/`-CSVs zurückführbar. S37-Test: pro KPI im Frontend (`2.635 Quellen`, `16.084 Personen`) die zugrunde liegende Aggregations-Logik im Code dokumentieren.

### Frontend (statistics.html + statistics.js)

4. **Default-Anzeige %.** Timeline-Balken zeigt zwei Layer pro Dekade:
   - Hintergrund (grau): `all_in_repo.total`
   - Vordergrund (blau): `released.total`
   - Tooltip: "X von Y Quellen ausgewertet (Z%)"

5. **Toggle "% / absolut".** Stakeholder kann zwischen Verhältnis-Ansicht und absoluter Ansicht wechseln. Default %.

6. **KPI-Anpassung.**
   - "2.635 Quellen aus mehreren Quellenkorpora" → "2.601 Quellen aus geprüften Korpora (QGW II/1, Stadtbuch Bd. 1) plus 34 in Vorbereitung (QGW II/2)" oder ähnlich, abhängig von V1-Klärung.
   - "16.084 individuelle Personen" → angepasst nach V2-Filter, mit Hinweis auf Stand.
   - "♀ 4.224 · ♂ 11.860" → Prozent-Beschriftung "26% / 74%" sekundär.

7. **Datenstand-Fußzeile** prominenter (S aus Strang A "Befunde nicht im Protokoll").

## Akzeptanzkriterien

- [ ] `timeline.json` enthält `released`, `all_in_repo`, `ratio_released_pct` pro Dekade.
- [ ] Statistik-Page Default-Anzeige ist %.
- [ ] Toggle "% / absolut" funktional.
- [ ] Zwei-Layer-Balken (Hintergrund Gesamt, Vordergrund Released).
- [ ] KPI-Header ist mit released-Filter gemäß V1+V2 konsistent.
- [ ] Datenstand-Fußzeile prominent (Datum, Korpus-Stand).
- [ ] S37-Audit: jeder KPI-Wert auf eine identifizierbare Aggregations-Quelle zurückführbar.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `project/statistics.html` Timeline | gleiche URL | Alt: blaue Balken absolute Counts. Neu: zwei-Layer (grau Gesamtbestand, blau Released) plus % im Tooltip |
| 2 | KPI "2.635 Quellen" | gleiche URL | Alt: 2.635 absolut. Neu: gefilterte Zahl plus Erläuterung released |
| 3 | KPI "16.084 Personen" | gleiche URL | Alt: 16.084. Neu: gefilterte Zahl gemäß V2 |
| 4 | Toggle "% / absolut" | gleiche Page | Alt: nicht vorhanden. Neu: Toggle-Button vorhanden |
| 5 | Datenstand-Fußzeile | gleiche Page | Alt: dezent. Neu: prominenter |

## Risiken / Antipatterns

- **Risiko:** Stakeholder versteht Variante (b) nicht als "Gesamtbestand pro Dekade" sondern erwartet (a) — irreführend wenn nicht klar gelabelt.
- **Antipattern:** % ohne Audit-Spur. Jeder Wert muss rückrechenbar sein.
- **Antipattern:** Verschiedene KPI-Werte aus verschiedenen Aggregations-Quellen — erzeugt subtile Inkonsistenzen die Stakeholder fängt (S37-Verletzung).

## Anschluss

- Stakeholder-Issues: S12, S13, S26, S37.
- Voraussetzung: V1, V2 (Approval-Filter durchgängig).
- **User-Aktion vor Phase 4:** Datenbasis-Klärung (a/b/c-Variante).

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert.
