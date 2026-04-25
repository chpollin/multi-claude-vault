---
type: knowledge
vorschlag-id: V3
github-issue: 3
created: 2026-04-26
tags: [sugw, vorschlag, frontend, suche]
stakeholder-issues: [S16, S17, S18, S19, S20]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/static/js/index.js
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/static/js/register.js
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
aufwand: "8-12h"
status: ready-for-implementation
author: Koordinator
implementation-commits: []
---

# V3 — Suche: Volltext + ID + Diakritika-Normalisierung

## Problem

Stakeholder zentralster Befund (S16, S19): "Zentralstes Problem: alle Einträge zu Personen müssen auffindbar sein. Anhand von Stichproben ist davon auszugehen, dass derzeit im Schnitt 2/3 bis 3/4 aller Hits bei den Nennungen nicht angezeigt werden." Plus Smoking-Gun-Beispiel S20: "Simon Pötel" hat 0 Treffer in Dokumentensuche aber 40 in Personensuche; Regest 3819 enthält ihn nachweislich.

Strang A hat funktional bestätigt: substring-`indexOf` ohne Diakritika-Normalisierung. Schoenberg → 0 Treffer trotz Schönberg → 9; Mueller → 0 trotz Müller → 1. Der Suchindex `_s` wird in JS aus `n` (name), evtl. `id` zusammengesetzt — aber ohne Normalisierung und ohne Volltext-Erschließung der Regeste.

## Lösungsansatz

### Aggregator (Pipeline)

1. **Doppel-Index pro Suchfeld.** In `aggregator.py` für `persons_search.json`, `organisations_search.json`, `places_search.json` und `search.json`:
   - Originalfeld `n` bleibt wie ist.
   - Neues Feld `n_norm` = Diakritika-normalisiertes `n` (NFD + Filter Combining Marks + ä→ae, ö→oe, ü→ue, ß→ss).
   - Suchindex-Feld `_s` enthält `n + " " + n_norm + " " + id` (alle drei suchbar).

2. **Volltext-Erschließung der Regeste in `search.json`.** Pro Doc ein Feld `_ft` (full text) mit dem Regest-Volltext, Diakritika-normalisiert. Erlaubt Dokumentensuche nach Personen-Schreibungen, die im TEI als `<rs>` verzeichnet sind.

3. **Person → Erwähnungs-Liste** in `persons_search.json`: Feld `mentions` mit Liste der Doc-IDs (released Korpora). Suchergebnis kann Mention-Count anzeigen.

### Frontend (JS)

In `static/js/index.js` und `register.js`:

1. Filter-Funktion vor Suche anwenden: Eingabe Diakritika-normalisieren mit gleicher Funktion wie Aggregator.
2. Suche gegen `_s`-Feld (enthält original + normalisiert + id).
3. Multi-Word-AND beibehalten.
4. Optional: Trefferanzeige zeigt sowohl Mention-Count als auch Direkt-Treffer-Position.

### Globale Suchleiste

Stakeholder S17 ("Wonach sucht die Suchleiste?"): Hilfe-Tooltip an jeder Suchbox, der die Suchsemantik erklärt: "Diese Suche findet IDs, Namen (auch mit/ohne Umlaut) und Volltexte der Regeste." Implementiert in V6 (Glossar/Mouse-Over).

## Akzeptanzkriterien

- [ ] **Test-Anker S20 erfolgreich:** Suche "Simon Pötel" auf `documents.html` findet Regest 3819. Auf `register/persons.html` findet 40+ Personen-Einträge mit "Pötel".
- [ ] Suche "Schoenberg" findet alle 9 "Schönberg"-Treffer (= ASCII-Variante = Umlaut-Variante).
- [ ] Suche "Schönberg" findet alle 9 Treffer plus etwaige reine ASCII-Schreibungen.
- [ ] Suche nach Person-ID `pe__hadmar_von_schoenberg_QGW_II_I_1` findet exakt diese Person.
- [ ] Suche "Mueller" findet alle "Müller"-Personen.
- [ ] Stichproben: 5 weitere Stakeholder-bekannte Namen mit erwarteter Treffer-Zahl ausgehandelt (vor Implementation einholen).
- [ ] Performance: Index-Größe in `persons_search.json` höchstens verdoppelt (zumutbarer Bandbreitenkostenfaktor).

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `register/persons.html` Suche "Schoenberg" | gleiche Suche | Alt: 0 Treffer. Neu: 9+ Treffer |
| 2 | `register/persons.html` Suche "Müller" | gleiche Suche | Alt: 1. Neu: 1+ Treffer (Müller findet identisch + ggf. weitere) |
| 3 | `documents.html` Suche "Simon Pötel" | gleiche Suche | Alt: 0. Neu: ≥1 (mindestens Regest 3819) |
| 4 | `documents.html` Suche "Anna Pötlin" | gleiche Suche | Alt: 1. Neu: ≥1 (inkl. Regest 3819) |
| 5 | `register/persons.html` Suche `pe__hadmar_von_schoenberg_QGW_II_I_1` | gleiche Suche | Alt: ggf. 0. Neu: 1 Treffer (exakte ID-Suche) |

## Risiken / Antipatterns

- **Antipattern:** Normalisierung nur im Frontend. Index-Datei muss normalisiert sein, sonst hilft Frontend-Normalisierung nicht.
- **Antipattern:** Volltext im JSON unbeschränkt — kann Datei-Größe explodieren. Mitigation: Volltext-Felder pro Doc max. 5000 Zeichen, oder nur die Regest-Sektion.
- **Risiko:** False-Positive-Treffer bei sehr kurzen Eingaben ("e" findet alles). Bestehender Multi-Word-AND-Filter bleibt erhalten, kompensiert.
- **Risiko:** Performance-Hit bei JS-Filterung großer JSON-Indizes. Aktuell läuft das schon auf 16k Einträgen — Verdopplung ist akzeptabel.

## Anschluss

- Stakeholder-Issues: S16, S17, S18, S19, S20. Plus S22 (Personen-Profil zeigt Erwähnungen — eng mit `mentions`-Feld verknüpft).
- Verwandte V-IDs: V4 (Personen-Profile nutzen `mentions`), V6 (Mouse-Over erklärt Suchsemantik).
- Test-Anker: Regest 3819, Personen "Simon Pötel", "Anna Pötlin", "Hadmar von Schönberg".

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert nach Strang A's funktionaler Verifikation und Strang B's S20-Smoking-Gun.
