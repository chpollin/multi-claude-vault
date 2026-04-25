---
type: knowledge
vorschlag-id: V10
created: 2026-04-26
tags: [sugw, vorschlag, frontend, exploration]
stakeholder-issues: [S32, S33, S34]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/exploration_places.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/exploration_transactions.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/base.html (Top-Nav)
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/build.py (Routing)
aufwand: "3-5h"
status: ready-for-implementation
author: Koordinator
implementation-commits: []
---

# V10 — Exploration aufräumen

## Problem

S32 (Slide 11, Protokoll Z.22): "Exploration/Orte: Orte einstweilen ganz weglassen, da diese Kategorie noch ganz unsystematisch erfasst ist." S33 (Slide 11): "Siedlungskarte lädt nicht" — wird mit S32 hinfällig wenn Page entfernt. S34 (Protokoll Z.23, Slide 12): "Exploration/Transaktionen: Irreführende Daten, da keine Informationen über den Erarbeitungsgrad der Quellen und die Menge an verfügbaren Quellen angegeben werden."

Strang A bestätigt: `exploration/places.html` mit Siedlungskarte und Ortsregister vorhanden; `exploration/transactions.html` mit Verb-Browser und drei weiteren Sub-Sektionen.

## Lösungsansatz

### exploration/places.html — Stakeholder-Wunsch: weglassen

Drei Optionen:

- (a) **Page komplett entfernen** (Build überspringt das Template, Top-Nav-Eintrag entfernen). Direktlink wäre 404.
- (b) **Page mit "in Bearbeitung"-Hinweis ersetzen** (Inhalt-Stub, klare Stakeholder-Botschaft).
- (c) **Page erhalten, aber aus Top-Nav entfernen** (analog Q-Kategorie-Hybrid in V7).

**Empfehlung:** Variante (b) — kein 404, klares Signal. Stakeholder-Klärung ob (a) oder (b) bevorzugt; (c) ist konsistent mit V7-Hybrid-Ansatz aber stakeholder-wunsch-unklar.

### exploration/transactions.html — kontextualisieren

Stakeholder fordert nicht Entfernung, sondern Kontext. Page bleibt, ergänzt um:

1. **Datenstand-Banner oben:** "Diese Auswertung umfasst Quellen aus QGW II/1 und Stadtbuch Bd. 1 (Stand: <Datum>). Erarbeitungsgrad: X Quellen ausgewertet von Y Gesamtbestand (Z%)."
2. **Erarbeitungsgrad-Indikator** pro Sub-Sektion (Transaktionstypen, Verb-Browser, Institutionelle Empfänger, Institutionstyp×Transaktionstyp).
3. **Hinweis bei niedrigen Counts:** Sub-Sektion zeigt Hinweis "Datenbasis dünn — Aussagekraft begrenzt" wenn Counts unter Schwellenwert.

### Top-Nav

4. Top-Nav-Dropdown "Exploration" überarbeiten:
   - "Orte" entfernen (oder als "in Bearbeitung" markieren analog Register-Disabled-Pattern).
   - Hub-Link `/exploration/index.html` hinzufügen (Strang A: aktuell fehlt der Link zum Hub).
5. Routing: bei Variante (a) 404; bei (b)+(c) Page bleibt.

## Akzeptanzkriterien

- [ ] `exploration/places.html` ist gemäß Stakeholder-Entscheidung (a/b/c) behandelt.
- [ ] Top-Nav "Exploration" enthält keinen direkten Link auf "Orte" (oder als disabled markiert wie Register).
- [ ] `exploration/transactions.html` zeigt prominent den Datenstand-Banner mit Erarbeitungsgrad.
- [ ] `exploration/index.html` ist im Top-Nav-Dropdown verlinkt.
- [ ] Sub-Sektionen mit dünner Datenbasis tragen Hinweis-Banner.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `exploration/places.html` | gleiche URL | Alt: Siedlungskarte (defekt) + Ortsregister. Neu (Variante b): "in Bearbeitung"-Hinweis |
| 2 | Top-Nav "Exploration" Dropdown | gleiche Aktion | Alt: enthält "Orte". Neu: "Orte" entfernt oder disabled; Hub-Link ergänzt |
| 3 | `exploration/transactions.html` oberer Bereich | gleiche URL | Alt: keine Banner. Neu: Datenstand-Banner mit Erarbeitungsgrad |
| 4 | `exploration/transactions.html` Sub-Sektion mit dünner Datenbasis | gleiche URL | Alt: keine Warnung. Neu: Hinweis-Banner |

## Risiken / Antipatterns

- **Antipattern:** Page einfach 404 setzen (Variante a) ohne Stakeholder-Bestätigung. Stakeholder kann später fragen "wo ist die Page hin" — unangenehm.
- **Risiko:** Erarbeitungsgrad pro Sub-Sektion erfordert Aggregations-Detaildaten — kann Implementations-Aufwand vergrößern. Mitigation: Phase-4-MVP zeigt globalen Erarbeitungsgrad pro Page; Sub-Sektion-Detail in Phase-5-Iteration.

## Anschluss

- Stakeholder-Issues: S32, S33, S34.
- **User-Aktion vor Phase 4:** Stakeholder-Klärung für Variante (a/b/c) auf places.html.
- Verwandte V-IDs: V8 (Statistiken — Erarbeitungsgrad-Berechnung wiederverwendbar); V9 (Verb-Browser bleibt auf transactions.html).

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert.
