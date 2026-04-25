---
type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [project, sugw, roadmap, frontend]
status: active
---

# sugw Frontend-Rework Roadmap

Operationaler Plan für die Frontend-Überarbeitung. Fünf Phasen, mit klarer Übergabe zwischen ihnen und vollständiger Traceability vom Stakeholder-Feedback bis zur Verifikation.

## Vollständigkeitsprinzip

Kein Stakeholder-Feedback-Punkt darf unterschlagen oder still abgewählt werden. Jeder Punkt aus Protokoll und PPT bekommt:

- eine **Stakeholder-Issue-ID** (S1, S2, … in [[Findings/2026-04-26 - sugw Stakeholder-Feedback]])
- mindestens einen **Vorschlag** (V-ID, in `Project/sugw-Vorschläge/`)
- einen **Implementierungs-Status** (offen / in Arbeit / implementiert / abgelehnt mit Begründung)
- eine **Verifikations-Anleitung** (was, wo, wie zu testen)

Wenn ein Punkt aus methodischen oder technischen Gründen nicht umsetzbar ist, wird das mit Begründung dokumentiert — nicht ignoriert.

Die [[Project/sugw-Traceability-Matrix]] (wird in Phase 2 angelegt) ist die zentrale Tabelle, die alle vier Achsen verbindet.

## Phase 1 — Inspektion und Befunderhebung

Drei parallele Stränge, eventually consistent über den Vault:

**Strang A — Frontend-Inspektion am laufenden Server.** Subagent A. Output: `Findings/2026-04-26 - sugw Frontend-Inspektion.md`. Server: `http://127.0.0.1:8765/`.

**Strang B — Stakeholder-Feedback-Analyse.** Subagent B. Output: `Findings/2026-04-26 - sugw Stakeholder-Feedback.md`. Quellen: Protokoll-DOCX und PPT in Downloads.

**Strang C — Daten-Architektur dokumentieren.** Koordinator. Output: `Knowledge/sugw Daten-Architektur.md` — TEI → Build → Frontend mit Korpus-Differenzierung.

Eintrittsbedingung Phase 2: alle drei Outputs existieren und sind als `status: complete` markiert.

## Phase 2 — Synthese und Traceability-Matrix

Koordinator (Single-Claude-Curator):

- Befunde aus A+B+C zusammenführen.
- [[Project/sugw-Traceability-Matrix]] anlegen mit Spalten: `S-ID | Stakeholder-Aussage | Slide/Protokoll-Quelle | Betroffene Page/Komponente | Schicht | Schweregrad | Vorschlag-ID | Implementation-Status | Verification-Doc`.
- Pro Stakeholder-Issue mindestens einen Vorschlag zuweisen.
- Output: [[Sessions/2026-04-26 - sugw Synthesis 1]] als Lage-Notiz mit Quality Flags (V17-Pilot) und Liste der Vorschlags-IDs.

Eintrittsbedingung Phase 3: Traceability-Matrix vollständig (jede S-ID hat mindestens eine V-ID).

## Phase 3 — Konkrete Vorschläge ausarbeiten

Pro priorisiertem Vorschlag ein eigenes Dokument in `Project/sugw-Vorschläge/V<id> - <kurztitel>.md`. Vorlage in [[Templates/Template-sugw-Vorschlag]] (wird in Phase 2 angelegt). Inhalt:

- Frontmatter mit `vorschlag-id`, `stakeholder-issues` (Liste der S-IDs), `betroffene-files` (Pfade in sugw-Pipeline-Repo), `aufwand` (Stunden-Kontingent grob), `status: draft | review | ready-for-implementation | implementiert | abgelehnt`
- Problem (1-2 Absätze)
- Lösungsansatz (technisch konkret: welche Files, welche Daten-Strukturen, welche Templates)
- Akzeptanzkriterien (was muss erfüllt sein, damit der Vorschlag als implementiert gilt)
- Verifikations-Plan (welche URLs, welche Klick-Pfade, was der User sehen wird)
- Mögliche Antipatterns / Fallstricke
- Anschluss (Querbezüge zu anderen V-IDs)

Initial geplante Vorschläge (wird nach Phase 1+2 final):

- V1 — Korpuskontrolle und Approval-Marker (Datenmodell, Pipeline)
- V2 — Filterung der Indizes auf geprüfte Korpora (Pipeline + Frontend)
- V3 — Suchfunktion: Volltext + ID + Umlaut-Behandlung (Frontend-JS + Daten-JSON)
- V4 — Personen-Profile parallel zu Regesten (Build + Templates + Routing)
- V5 — Bidirektionale Verlinkung Person ↔ Urkunde (Daten + Templates)
- V6 — Glossar (Inhalt + Page-Struktur)
- V7 — Terminologie-Refactoring ("Factoids", "Tod" → "als verstorben genannt", Q-Kategorie)
- V8 — Statistiken: % statt absolute Quellenmenge pro Dekade (Pipeline-Aggregation)
- V9 — Verb-Browser-Aggregation (Daten + Frontend)
- V10 — Exploration: Orte ausblenden / Transaktionen kontextualisieren

Eintrittsbedingung Phase 4: alle Vorschläge mit Status `ready-for-implementation`, Akzeptanzkriterien explizit.

## Phase 4 — Implementierung in neuem sugw-Branch

Implementierung erfolgt im **Pipeline-Repo** `db_for_medieval_legal_transactions` (nicht im Edition-Repo — das ist Build-Output). Neuer Branch dort: `frontend-rework-2026-04` (oder analoger Name).

Workflow pro Vorschlag:

1. Implementation-Agent (Subagent) übernimmt einen Vorschlag.
2. Liest die V-Datei vollständig.
3. Implementiert in der Pipeline (Templates / Build-Code / Daten-Aggregation).
4. Lokaler Build (`python -m edition build` oder analog).
5. Lokal serven (Edition-Repo `python -m http.server 8766` parallel zum Original-Server auf 8765).
6. Akzeptanzkriterien gegen die neue Frontend-Version durchgehen.
7. Verifikations-Anleitung als eigene Datei in `Project/sugw-Verifikation/V<id>-Verifikation.md` schreiben (Template in [[Templates/Template-sugw-Verifikation]], wird in Phase 3 angelegt).
8. V-Datei auf `status: implementiert` setzen, Traceability-Matrix updaten.
9. Sessionende-LOG-Eintrag im V-Doc.

Hard-Constraints:

- KEINE direkten Commits auf `main` des Pipeline-Repos. Nur auf Branch `frontend-rework-2026-04`.
- KEIN Push auf Remote ohne explizite User-Freigabe (git-Safety-Protokoll).
- KEINE Änderungen außerhalb der für den Vorschlag freigegebenen Files (V13-opt-in: V-Datei trägt `betroffene-files` als Lock-Liste).
- Bei Konflikt zwischen zwei Vorschlägen, die die gleiche Datei berühren: Hinweis in [[COORDINATION#Hinweise]], Eskalation an Koordinator.

Vergleich alt/neu:

- Original-Frontend bleibt unter `http://127.0.0.1:8765/` erreichbar (Edition-Repo `main`-Branch-Stand).
- Neues Frontend unter `http://127.0.0.1:8766/` (Build-Output von `frontend-rework-2026-04`).
- User kann beide Tabs nebeneinander aufmachen, Verifikations-Doc in der Hand.

Eintrittsbedingung Phase 5: alle Vorschläge mit Status `implementiert` UND zugehörige Verifikations-Docs vorhanden.

## Phase 5 — Verifikations-Dokumentation für den User

Konsolidiert aus den V-Verifikations-Docs:

- [[Project/sugw-Verifikations-Master.md]] — eine konsolidierte Anleitung in einem Dokument: pro V-ID Schritt-für-Schritt-Test, alt-vs-neu-URL, erwartetes Ergebnis, Stakeholder-Issue-Referenz.
- Plus eine Top-Level-Checkliste, die der User abarbeiten kann.
- Plus Hinweis auf nicht-implementierte / abgelehnte Stakeholder-Issues mit Begründung.

Output:

1. [[Project/sugw-Verifikations-Master.md]] — User-Anleitung.
2. [[Sessions/2026-04-26 - sugw Implementation Closure]] — Lage-Notiz mit Vollständigkeits-Check (jeder S-ID ist eine V-ID zugewiesen, jede V-ID hat Status, jede implementierte V-ID hat Verifikations-Doc).
3. Pull-Request-Beschreibung-Stub für den sugw-Pipeline-Branch (für späteren PR ans sugw-`main`).

## Phase 6 — Reflux zur Mother

Methodische Lessons aus Phase 1–5 dokumentieren als Findings mit `reflux-target: main@multi-claude-vault`. Erwartete Themen:

- Wie hat die Drei-Rollen-Methode in einem realen Projekt mit echten Stakeholdern getragen?
- V15-Pilot: hat die No-shared-write-Klausel funktioniert? Race Conditions zwischen Subagents?
- V20: hat Stellungnahmen-Schreibhoheit auch für externe Stakeholder-Aussagen funktioniert (Agent B durfte nicht ausschmücken)?
- V13: hat Files-locked-Konvention für parallele Implementation-Subagents getragen?
- V17 Validation-Loop: hat das Quality-Flag-Format Stakeholder-Akzeptanz tatsächlich operationalisiert?

## Status

- Phase 1 in Bearbeitung. Branch `sugw-frontend-rework` von `main@e355bac` abgezweigt.
- Server läuft auf `http://127.0.0.1:8765/`.
- Subagent-Prompts in [[Project/sugw-Subagent-Prompts]] für Phase 1 (Agent A, B), Phase 4 (Implementation-Agent), Phase 5 (Verifikations-Master-Konsolidierung).
- Eigener Strang C (Daten-Architektur) in Arbeit.

## Anschluss

- [[MISSION]] — Project-Fork-MISSION mit Forschungsfrage und Erfolgskriterien.
- [[METHOD]] — geerbte Methode aus Mother.
- [[Project/sugw-Subagent-Prompts]] — System-Prompts für alle Subagent-Phasen.
- [[Project/sugw-Traceability-Matrix]] — wird in Phase 2 angelegt.
- [[Knowledge/sugw Daten-Architektur]] — geplant, Strang C.
