---
type: knowledge
created: 2026-04-26
tags: [sugw, pr, stub]
status: phase-3-skeleton
author: Koordinator
---

# sugw Pull-Request-Stub

Vorbereitete PR-Beschreibung für den späteren Merge `frontend-rework-2026-04` → `main` im sugw-Pipeline-Repo. Wird in Phase 5 nach Implementation finalisiert mit konkreten Commit-Hashes und Diff-Stichworten.

---

## PR-Title (Vorschlag)

`Frontend-Rework auf Basis Stakeholder-Feedback Meeting 23.4.2026 (V1-V11)`

## PR-Beschreibung-Template

```markdown
## Zusammenfassung

Frontend-Refactoring der digitalen Edition basierend auf dem Stakeholder-Feedback-Meeting vom 23.4.2026 (Gonaus, Handl, Lutter, Siegl, Steinböck). Adressiert 37 Stakeholder-Issues (S1-S37) durch 11 strukturierte Vorschläge (V1-V11) mit klarer Traceability vom Feedback-Punkt bis zur Code-Änderung und Verifikations-Anleitung.

Methodisch durchgeführt im [chpollin/multi-claude-vault](https://github.com/chpollin/multi-claude-vault) Project-Fork (Branch `sugw-frontend-rework`) als Phase-E-Pilot der Multi-Claude-Vault-Methode.

## Kategorisierung der Änderungen

### Blocker-Issues (Stakeholder-zentral)

- **V1 Korpus-Approval-Marker:** Daten-Modell um Korpus-Marker pro Aggregat-Entität erweitert. `RELEASED_CORPORA`-Mechanismus durchgängig in `aggregator.py` angewandt.
- **V2 Filterung der Indizes:** Personen-/Org-/Place-Indizes und alle Statistiken zeigen nur released Korpora. Personen ohne Erwähnung aus Index entfernt.
- **V3 Suche:** Doppel-Index (original + Diakritika-normalisiert) in `_s`-Feld; Volltext-Erschließung der Regeste in `search.json`. Test-Anker S20 (Pötel/Pötlin/Regest 3819) erfüllt.
- **V4 Personen-Profile:** Eigene Detail-Page pro Person mit Erwähnungen, Beziehungen, Schreibvarianten.
- **V5 Bidirektionale Verlinkung:** Person ↔ Urkunde + Beziehungs-Sektion in Personen-Profil.

### Major-Issues

- **V6 Glossar mit Mouse-Over:** Glossar erweitert auf 14+ Begriffe; Tooltip-Komponente an Tabellen-Spalten-Header. Tooltips speisen sich aus zentralem `glossary.json`.
- **V7 Terminologie-Refactoring:** "Tod" → "als verstorben genannt"; "Factoid" → [Stakeholder-bestätigter Ersatz]; "Wiener Urkundenbuch" entfernt; "Überlieferungslücke" → "Auswertungslücke"; Q-Kategorie aus Top-Nav entfernt.
- **V8 Statistiken:** Default-Anzeige %; Toggle "% / absolut"; zwei-Layer-Balken (Gesamtbestand + Released). KPI-Header gefiltert.
- **V9 Verb-Browser-Aggregation:** Cluster-Heuristik mit manueller Pflege via `verb_clusters.csv`. Stakeholder-Beispielphrasen aus S35 zusammengefasst.
- **V10 Exploration aufräumen:** Orte-Sub-Page entfernt/markiert; Transaktionen mit Datenstand-Banner kontextualisiert.

### Minor-Issues

- **V11 Frontend-Polish:** Regestentext-Spaltenbreite, Wiener-Neustadt-Dublette, Nav-Disabled-Konsistenz, Datenstand-Fußzeile prominent, Exploration-Hub-Link im Dropdown.

## Methodisch dokumentiert (kein Code)

- **S30 Verbindung Interface ↔ Git-Repository:** dokumentiert in [Knowledge/sugw Daten-Architektur](../multi-claude-vault/Knowledge/sugw Daten-Architektur.md).
- **S36 DB-Vorrang:** als Out-of-Scope-Klausel in Project-Fork-MISSION verankert.

## Vollständigkeit

Jeder der 37 Stakeholder-Issues hat eine V-ID-Zuordnung in [Project/sugw-Traceability-Matrix.md](../multi-claude-vault/Project/sugw-Traceability-Matrix.md). Keine S-ID still abgewählt.

## Verifikation

Schritt-für-Schritt-Anleitung in [Project/sugw-Verifikations-Master.md](../multi-claude-vault/Project/sugw-Verifikations-Master.md). Vergleich auf Port 8765 (alt) vs. 8766 (neu).

## User-Klärungen pendent (vor Merge)

- (a) `RELEASED_CORPORA`-Liste: ist QGW II/2 (1415-1417) freigegeben oder nicht? (V1)
- (b) "Factoid"-Ersatzbegriff (V7) — Stakeholder-Präferenz aus drei Kandidaten ("Erwähnungen im Regest", "Strukturierte Nennungen", "Regest-Entitäten").
- (c) Q-Kategorie-Hybrid (V7) — Top-Nav-Entfernung mit Direktlink-Erhalt.
- (d) Glossar-Begriffsliste (V6) — vollständige Stakeholder-Bestätigung.
- (e) "Aaron der Jude" / Personen mit 0 Dokumenten Datenbasis-Klärung (V2).
- (f) `exploration/places.html` Variante (a/b/c) (V10).
- (g) Datenbasis "Gesamtbestand pro Dekade" für V8 (Variante a/b/c).
- (h) Verb-Cluster-Schwellenwert N (V9).

## Test-Plan

- Lokale Vergleichsserver auf Port 8765 (main) und 8766 (frontend-rework-2026-04).
- Pipeline-Tests: `python -m pipeline test` (Regression).
- Edition-Tests: `python -m pytest edition/tests/`.
- Stakeholder-Stichproben gemäß `Project/sugw-Verifikations-Master.md`.
- Performance-Check: Build-Zeit-Regression nicht > Faktor 2.

## Änderungs-Volumen (Schätzung, wird nach Implementation aktualisiert)

- ~25 Pipeline-/Aggregator-Files
- ~15 Templates
- 3 neue JS-Module (Tooltip, ggf. Suche-Erweiterung, ggf. Statistik-Toggle)
- 1 neuer Markdown (`glossary.md`)
- 1 neue Normalisierungs-Tabelle (`verb_clusters.csv`)
- ~10.000-12.000 neue Personen-Detail-Pages

## Reviewer-Empfehlung

- Datenmodell-Review: V1, V2 (Approval-Mechanismus durchgängig).
- Code-Review: V3, V4, V5 (zentrale Funktionalität).
- Inhalts-Review: V6, V7 durch Stakeholder.
- Performance-Review: V4 (Build-Zeit, Page-Anzahl).

🤖 Generiert mit [Claude Code](https://claude.com/claude-code)
```

## Pre-Merge-Checkliste

- [ ] Alle 11 V-Docs `status: implementiert`.
- [ ] Alle V-Verifikations-Docs `status: bestätigt-vom-user`.
- [ ] Alle 37 S-IDs in Traceability-Matrix mit Status `implementiert` oder `dokumentiert` oder `abgelehnt-mit-Begründung`.
- [ ] Pipeline-Tests grün.
- [ ] Edition-Tests grün.
- [ ] Stakeholder-Stichproben aus Verifikations-Master verifiziert.
- [ ] User-Klärungen (a)-(h) abgeschlossen.

## Anschluss

- [[Project/sugw-frontend-rework Roadmap]] — Phasen-Plan.
- [[Project/sugw-Traceability-Matrix]] — vollständige Issue/V-ID-Zuordnung.
- [[Project/sugw-Verifikations-Master]] — User-Verifikations-Anleitung.
- [[MISSION]] — Project-Fork-MISSION.
