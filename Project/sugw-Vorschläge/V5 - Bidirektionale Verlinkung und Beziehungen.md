---
type: knowledge
vorschlag-id: V5
github-issue: 5
created: 2026-04-26
tags: [sugw, vorschlag, frontend, verlinkung]
stakeholder-issues: [S22, S23, S24]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/person_detail.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/document.html
aufwand: "6-8h"
status: ready-for-implementation
author: Koordinator
implementation-commits: []
---

# V5 — Bidirektionale Verlinkung Person ↔ Urkunde + Beziehungen

## Problem

S24 (Blocker, Protokoll Z.16): "Die ID der Person ist zu jeder Urkunde verlinkt, in der sie vorkommt — umgekehrt wäre das auch notwendig für das Profil der Person." S23: "Verwandtschaftsbeziehungen sind ausgewiesen, aber im Frontend nicht einsehbar." S22: Profil zeigt Beziehungen.

Strang A bestätigt: Hin-Richtung (Urkunde→Person) existiert via Anker. Rück-Richtung fehlt strukturell weil keine Detail-Page. Mit V4 (Detail-Pages) wird die Rück-Richtung baulich möglich; V5 spezifiziert die konkrete Daten-Aggregation.

## Lösungsansatz

### Aggregator (Pipeline)

1. **Inverser Index Person → Urkunden.** Aus `persons_in_sources.csv` Aggregation: pro `pe_id` Liste der `doc_id`s plus Rolle und Datum. Wird im Personen-Aggregat (V4 `persons/<pe_id>.json`) im Feld `mentions[]` materialisiert.

2. **Beziehungs-Aggregation.** Aus `*_relations_in_sources.csv` (kin, occ, owner, friend, rep, tenant, title-ref, topo, buis):
   - Pro `pe_id` Liste der Relationen mit `{type, partner_id, partner_name, source_doc, source_excerpt}`.
   - Symmetrische Relationen (kin, friend) werden in beiden Personen-Aggregaten materialisiert.
   - Asymmetrische (owner, rep, tenant) nur in der jeweiligen Rolle.

3. **Cross-Reference-Konsistenz-Check.** Beim Build prüfen: für jede Urkunde mit `<rs type="person" ref="#pe_id">` muss `pe_id` in `persons_search.json` existieren (released gefiltert). Lose Refs werden in einem Build-Report dokumentiert.

### Templates

- `person_detail.html` (V4) Sektion "Erwähnungen": Tabelle `Doc-ID | Datum | Rolle | Regest-Excerpt` mit Klick-Through.
- `person_detail.html` Sektion "Beziehungen": gruppiert nach Beziehungstyp, Verlinkung auf Partner-Person/-Org.
- `document.html` Sektion "Personen": jede `<rs type="person">` linkt auf `register/persons/<pe_id>.html` (statt Anker).

### Test-Anker S20-konform

Beim Anschauen von "Simon Pötel"-Profil: Regest 3819 erscheint in `mentions[]`. Beziehung "Ehemann von Anna Pötlin" erscheint in Beziehungs-Sektion. Klick auf "Anna Pötlin" navigiert zu deren Profil, wo Regest 3819 ebenfalls erscheint plus Beziehung "Ehefrau von Simon Pötel".

## Akzeptanzkriterien

- [ ] Personen-Profil zeigt Liste aller Erwähnungen aus released Korpora mit Doc-ID, Datum, Rolle, Excerpt.
- [ ] Personen-Profil zeigt Beziehungen gruppiert nach Typ.
- [ ] Klick auf Erwähnung navigiert zur Urkunden-Detail-Page.
- [ ] Klick auf Beziehungs-Partner navigiert zu Partner-Profil.
- [ ] Aus Urkunden-Detail Klick auf `<rs type="person">` führt zur Detail-Page (statt Anker).
- [ ] Test-Anker S20 erfüllt: Simon Pötel Profil zeigt Regest 3819 + Anna Pötlin als Beziehung; Anna Pötlin Profil symmetrisch.
- [ ] Build-Report listet lose Refs (falls vorhanden).

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `register/persons.html#pe__simon_poetel_*` | `register/persons/pe__simon_poetel_*.html` | Alt: Anker. Neu: vollständiges Profil mit Erwähnungen + Beziehungen |
| 2 | Profil-Sektion "Beziehungen" für Simon Pötel | — | Eintrag "Ehefrau: Anna Pötlin" mit klickbarem Link |
| 3 | Klick auf Anna Pötlin im Profil | — | Navigation zu Anna-Pötlin-Profil; symmetrische Beziehung "Ehemann: Simon Pötel" |
| 4 | Aus Regest 3819 Klick auf Personen-Eintrag | gleiche Aktion | Alt: Anker in `register/persons.html`. Neu: Personen-Detail-Page |

## Risiken / Antipatterns

- **Risiko verwaiste Refs:** TEI-References auf Personen, die durch released-Filter aus dem Index fallen. Build-Report dokumentiert; Frontend-Templates müssen graceful degradieren (Anzeige als Plain-Text mit Hinweis "Eintrag nicht in geprüftem Korpus").
- **Antipattern:** Beziehungen nur einseitig materialisieren. Symmetrie muss explizit (Anna→Simon UND Simon→Anna) bei kin/friend.
- **Antipattern:** Beziehungen ohne Quellen-Beleg. Jede Beziehung muss Source-Doc-Verweis tragen, sonst nicht falsifizierbar.

## Anschluss

- Stakeholder-Issues: S22, S23, S24.
- Voraussetzung: V4 (Detail-Pages); V1+V2 (Filter).
- Synergie mit V4 — gemeinsamer Implementations-Block sinnvoll.

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert.
