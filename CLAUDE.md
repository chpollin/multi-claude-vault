---
type: vault-organisation
created: 2026-04-25
updated: 2026-04-26
tags: [meta, coordination]
status: active
---

# RULES — multi-claude-vault

Werkstatt eines Forschungsprojekts: parallele Claude-Code-Instanzen entwickeln eine Methode für die kollaborative Vault-Arbeit, indem sie sie anwenden. Selbstreferentiell. Der parallele Lesevault `c:/Users/Chrisi/Documents/obsidian` ist Wissensquelle und bleibt unangetastet — hier wird gearbeitet, dort wird gelesen.

## Aktueller Stand (2026-04-26, Branch sugw-frontend-rework — Phase-E-Pilot)

**Project-Fork-Modus aktiv.** Dieser Branch ist erste Anwendung der Methode an einem realen Projekt: sugw-Frontend-Refactoring auf Basis Stakeholder-Feedback (Meeting 23.4.2026). Mother-Vault auf `main` trägt die Methode (V1–V8 ratifiziert + Vier+1-Schichten); Fork hat eigene MISSION mit Projektziel (siehe [[MISSION]]).

**Drei-Rollen-Aufstellung:**
- **Claude A** (Tech-Strang): Frontend-Inspektion → Tech-Vorschläge V1-V5/V8-V10 → Implementation in sugw-Pipeline-Repo Branch `frontend-rework-2026-04` → Tech-Verifikations-Docs.
- **Claude B** (Inhalt-Strang): Stakeholder-Feedback-Analyse → Inhalts-Vorschläge V6 (Glossar) + V7 (Terminologie) → Inhalts-Implementation → Stakeholder-Verifikations-Mapping.
- **Koordinator** (Single-Curator, diese Session): Strang C (Daten-Architektur) → Synthese + Traceability-Matrix → Konflikt-Koordination → Verifikations-Master + PR-Stub → Reflux-Findings für Mother.

**Vollständigkeitsprinzip:** kein Stakeholder-Feedback-Punkt darf still abgewählt werden. Jede S-ID hat mindestens eine V-ID, jede V-ID hat Implementation-Status, jede implementierte V-ID hat Verifikations-Doc. Tracking in [[Project/sugw-Traceability-Matrix]].

**Live-Server:** `http://127.0.0.1:8765/` (Original-Frontend, Edition-Repo). Ab Phase 4 zusätzlich `http://127.0.0.1:8766/` (Build-Output von `frontend-rework-2026-04`).

**Phasen-Status:** Phase 1 (Inspektion) parallel in Bearbeitung. Phase 2 (Synthese) wartet auf Outputs A+B+C. Phase 3-5 sequenziell danach. Phase 6 (Reflux zur Mother) am Ende.

**Mother-Stand auf main:** Phase A (Methoden-Reife) und Phase B (Strukturkonsolidierung) abgeschlossen. METHOD trägt 5 ratifizierte Items (V1, V2, V3, V6, V8) plus Vier+1-Schichten-Architektur. 12 weitere V-Items konsensreif. Distributionsfähiger Template-Vault.

Repo: [chpollin/multi-claude-vault](https://github.com/chpollin/multi-claude-vault). Lizenz MIT.

## Identität

Identifikator ist die Rolle, nicht eine Sessionnummer. Drei Rollen, abgestimmt mit der Rollenkarte im Lesevault ([VAULT-OPERATIONS#Rollen](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)):

- **Vault-Architekt / Strukturarbeiter** — *am* Vault: Form, Struktur, Steuerungsdokumente, Konventionen.
- **Operativer Koordinator** — *quer durch* den Vault: Cross-Project-Sicht, Synthese-Verantwortung, Lage-Notizen, Validation-Loop.
- **Inhalt** — substantielle Methoden-Drafts, Falldaten-Pflege, Wissenssynthesen, Pattern-Bibliothek.

Rollen werden vom User beim Sessionstart zugewiesen. Beitragsdateien in `Roles/` (V9, Single Source für Identität).

## Dokumentstruktur (Vier+1-Schichten)

Volle Beschreibung in [[METHOD#Vier+1-Schichten-Architektur (V7 + V14b + V19)]].

| Schicht | Dateien | Lifecycle |
|---|---|---|
| 1 — Stabile Anker | [[MISSION]], [[CLAUDE]], [[METHOD]], `Project/INDEX|DATA|REQUIREMENTS|DESIGN` | stabil bzw. wachsend |
| 2 — Lebende Koordination | [[COORDINATION]], [[LOG]], [[BACKLOG]], `Project/JOURNAL` | ephemer / append-only / wandernd |
| 3 — Beiträge der Instanzen | `Roles/Claude-N`, `Roles/Beobachtung Claude-1` | rolle-gebunden, Schreibhoheit beim Slot |
| 4 — Forschungsmaterial | `Sessions/`, `Findings/`, `Experiments/` | kumulativ, Datums-Naming |
| 5 — Concepts (V19) | `Concepts/` | kollektiv, V19 pendent |

Parallele Klassen: `Knowledge/` (eigene Synthesen), `Literature/` (annotated bibliography), `Templates/` (Vorlagen), `instances/` (V15 Subagent-Namespaces), `_archive/`.

## Rituale

**Sessionstart**

1. Reihenfolge lesen: CLAUDE → MISSION → METHOD → COORDINATION (oben + eigene Rollensektion) → LOG (letzte 10 Einträge) → BACKLOG → eigene Beitragsdatei in `Roles/`.
2. Eigenen Eintrag in COORDINATION unter `## Aktive Sessions` setzen oder aktualisieren (`last-touch` auf heute).
3. LOG-Eintrag: "Session gestartet, Rolle X, Fokus Y".

**Pre-Edit-Read** (V6, vor jedem Edit an einem geteilten Dokument)

- Wenn letzter Read mehr als ~10 min her: re-read.
- Bei "modified since read"-Konflikt: nicht überschreiben, re-read und prüfen ob fremde Änderung den eigenen Edit obsolet macht.
- COORDINATION auf `Files locked` (V13 opt-in für mehrstufige Eingriffe) prüfen; eigene Edits dort kurz markieren.

**Sessionende**

1. Eigenen Eintrag in COORDINATION entfernen oder mit `[abgeschlossen]` markieren.
2. LOG-Eintrag mit Kernarbeit der Session.
3. Beitragsdatei in `Roles/` auf Sessionende-Stand aktualisieren.

**Konflikt** — bei kollidierender Edit-Absicht oder inhaltlicher Differenz: nicht überschreiben, nicht überreden. Hinweis in COORDINATION unter `## Hinweise`, Eskalation an User. Stellungnahmen sind Schreibhoheit der jeweiligen Rolle (V20) — keine Stellungnahmen in fremdem Namen verfassen.

## Quellenbezug zum Lesevault

Inhalte aus dem Lesevault werden zitiert über Markdown-Links mit absolutem Pfad (z.B. `[VAULT-OPERATIONS](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)`). Wikilinks `[[...]]` wirken nur innerhalb dieses Vaults; cross-vault muss als Markdown-Link.

**Niemals in den Lesevault zurückschreiben.** Reflux-Verbote in [[Knowledge/Cross-Vault-Methodik]].

## Anschluss

- [[HOME]] — Obsidian-Einstieg / MOC.
- [[MISSION]] — Forschungsfrage, Scope.
- [[METHOD]] — ratifizierte Methode mit Vier+1-Schichten-Architektur.
- [[BACKLOG]] — Methodendiskurs.
- [[Knowledge/Knowledge MOC|Knowledge MOC]] — Wissens-Hub.
- [[Project/INDEX]] — Promptotyping K/P/A-Selbstdokumentation des Projekts.
